# ReceiptVault — Claude AI Receipt Parsing Architecture

## Current Flow (OCR Only)
```
Receipt Image
    ↓
Apple Vision OCR (on-device, free)
    ↓
Raw Text Observations (position + text)
    ↓
Custom Parser (regex, sequential zip, heuristics)  ← FRAGILE
    ↓
Parsed Receipt (vendor, items, totals)
    ↓
Review Screen → Save to Supabase
```

**Problem:** Custom parser breaks on every new receipt format.

---

## New Flow (OCR + Claude AI)
```
Receipt Image
    ↓
Apple Vision OCR (on-device, free)
    ↓
Raw Text (all lines joined)
    ↓
Claude API (send raw text, get structured JSON)  ← SMART
    ↓
Parsed Receipt (vendor, items, totals)
    ↓
Review Screen → Save to Supabase
```

**Advantage:** Claude understands ANY receipt format. No regex, no heuristics.

---

## Detailed Architecture

### Step 1: Image Capture (unchanged)
```
Camera Scan / Digital Import / Voice
         ↓
      UIImage
```

### Step 2: OCR Text Extraction (unchanged, on-device)
```
UIImage
   ↓
VNRecognizeTextRequest (Apple Vision)
   ↓
["FARMERS INDIA MARKET",
 "1000 BOSTON TURNPIKE ROAD",
 "1 CAULIFLOWER  2 @ 2.50  5.00",
 "2 AVACADO BIG  3.98",
 ...
 "SubTotal: 194.87",
 "Total: 194.87"]
```

### Step 3: Claude API Call (NEW)
```
Send to Claude API:
┌─────────────────────────────────────────┐
│ SYSTEM PROMPT:                          │
│ You are a receipt parser. Extract:      │
│ - vendor_name                           │
│ - date (YYYY-MM-DD)                     │
│ - items[] (name, quantity, unit_price,  │
│   total_price)                          │
│ - subtotal, tax, total                  │
│ - payment_method                        │
│ Return valid JSON only.                 │
│                                         │
│ USER MESSAGE:                           │
│ Parse this receipt text:                │
│ [raw OCR text here]                     │
└─────────────────────────────────────────┘
              ↓
Claude Response (JSON):
┌─────────────────────────────────────────┐
│ {                                       │
│   "vendor_name": "Farmers India Market",│
│   "date": "2026-04-04",                │
│   "items": [                            │
│     {                                   │
│       "name": "CAULIFLOWER",            │
│       "quantity": 2,                    │
│       "unit_price": 2.50,              │
│       "total_price": 5.00              │
│     },                                  │
│     {                                   │
│       "name": "AVACADO BIG",            │
│       "quantity": 2,                    │
│       "unit_price": 1.99,              │
│       "total_price": 3.98              │
│     },                                  │
│     ...                                 │
│   ],                                    │
│   "subtotal": 194.87,                  │
│   "tax": 0.00,                         │
│   "total": 194.87,                     │
│   "payment_method": "Credit Card"       │
│ }                                       │
└─────────────────────────────────────────┘
```

### Step 4: Review & Save (unchanged)
```
JSON → ParsedReceipt → ReviewConfirmView → Supabase
```

---

## Code Changes

### New File: `ClaudeService.swift`
```
┌──────────────────────────────────┐
│ ClaudeService                     │
│                                   │
│ + parseReceipt(rawText: String)  │
│   → ParsedReceipt                │
│                                   │
│ - Sends raw OCR text to Claude   │
│ - Receives structured JSON       │
│ - Decodes into ParsedReceipt     │
│ - Falls back to OCR parser       │
│   if API fails                   │
└──────────────────────────────────┘
```

### Modified: `OCRService.swift`
```
Before:  recognizeText() → parseReceipt() → items
After:   recognizeText() → raw text → ClaudeService → items
                                         ↓ (fallback)
                                      parseReceipt() → items
```

### New File: `ClaudeSecrets.swift` (gitignored)
```
enum ClaudeSecrets {
    static let apiKey = "sk-ant-..."
}
```

---

## Fallback Strategy
```
         OCR Raw Text
              ↓
     ┌── Claude API ──┐
     │   (primary)     │
     ↓                 ↓
  Success?          Failed?
     ↓              (no internet, API error, timeout)
  Use Claude         ↓
  result          Fall back to
                  local OCR parser
                  (current code)
```

---

## API Cost Estimate
```
Claude Haiku (fast, cheap):
  ~500 tokens per receipt
  ~$0.001 per receipt ($1 per 1000 receipts)

Claude Sonnet (smarter):
  ~500 tokens per receipt
  ~$0.005 per receipt ($5 per 1000 receipts)

Recommendation: Use Haiku for receipts (fast + cheap + accurate enough)
```

---

## Security
- API key stored in `ClaudeSecrets.swift` (gitignored)
- Raw receipt text sent over HTTPS
- No images sent to Claude (only OCR text)
- No PII logged in production
- Fallback to offline OCR if API unavailable

---

## Implementation Time: ~3 hours
1. Create ClaudeService.swift (1 hr)
2. Modify capture flow to use Claude (1 hr)
3. Test with all receipt types (1 hr)
```

---

## Files Changed
```
NEW:  Services/ClaudeService.swift      — API client
NEW:  Services/ClaudeSecrets.swift      — API key (gitignored)
NEW:  Services/ClaudeSecrets.swift.example
MOD:  Views/Capture/DocumentScannerView.swift  — use ClaudeService
MOD:  Views/Capture/DigitalReceiptView.swift   — use ClaudeService
MOD:  .gitignore                               — add ClaudeSecrets.swift
```

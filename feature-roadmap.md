# ReceiptVault — Feature Roadmap

## Vision
Make ReceiptVault the only receipt app that **saves you money, protects your purchases, AND simplifies your taxes**.

---

## Tier 1 — Game Changers (Unique Differentiators)

### 1. Smart Budget Alerts
**What:** Proactive notifications based on spending patterns.
**Examples:**
- "You've spent $450 at restaurants this month — 30% more than last month"
- "Your grocery spending is trending up: $200 → $280 → $340 over 3 months"
- "You've hit 80% of your monthly dining budget"

**Why it matters:** No other receipt app provides proactive spending insights. Users stay engaged and make better financial decisions.

**Effort:** ~2 days

---

### 2. Receipt Warranty Tracker
**What:** Tag receipts with warranty expiry dates. Get reminders before they expire.
**Examples:**
- "Your Samsung TV warranty expires in 14 days — receipt saved"
- "3 items have active warranties"
- One-tap access to the receipt when you need to make a warranty claim

**Why it matters:** People LOSE receipts for warranty claims. This alone sells the app. Saves hundreds of dollars when electronics or appliances break.

**Effort:** ~2 days

---

### 3. Tax Category Auto-Tagging
**What:** Claude AI auto-categorizes each receipt for tax purposes. Export a tax-ready report at year end.
**Categories:**
- Business Expense
- Medical / Healthcare
- Charitable Donation
- Home Office
- Vehicle / Mileage
- Education
- Personal (non-deductible)

**Export:** "2026 Tax Deductions Report — $4,832 total across 127 receipts"

**Why it matters:** Accountants and freelancers would love this. Saves hours during tax season. Claude AI does the categorization automatically — no manual tagging.

**Effort:** ~1 day (Claude already parses receipts — just add category field to the prompt)

---

### 4. Price Comparison Over Time
**What:** Track prices of the same items across stores and over time.
**Examples:**
- "Milk at BJ's: $3.99 (Apr) vs $4.49 (Jan) — up 12%"
- "You paid less for eggs at Farmers India ($8.99) vs BJ's ($11.99)"
- "Cheapest place for Organic Milk: Farmers India Market ($11.99)"

**Why it matters:** Nobody does this. Users can see price inflation in real-time and choose the cheapest store for each item. Unique feature that drives word-of-mouth.

**Effort:** ~3 days (requires item-level matching across receipts)

---

### 5. Split Receipt with Friends/Family
**What:** Tap items on a receipt to assign to different people. Generate payment amounts.
**Flow:**
1. Open a restaurant/group receipt
2. Tap items → assign to "John", "Sarah", "Me"
3. Auto-calculate each person's share (including tax/tip split)
4. Share via text: "John owes $28.00, Sarah owes $24.50"

**Why it matters:** Perfect for group dinners, shared groceries, roommates. Currently people do this manually with calculators.

**Effort:** ~3 days

---

## Tier 2 — High Value (Competitive Advantages)

### 6. Expense Reports
**What:** One-tap expense report generation with receipt images.
**Output:** Professional PDF with:
- Date range
- Categorized expenses
- Receipt images attached
- Subtotals by category
- Grand total

**Target users:** Freelancers, small business owners, employees who expense meals/travel.

**Effort:** ~2 days

---

### 7. Recurring Purchase Detection
**What:** Detect buying patterns and remind when it's time to repurchase.
**Examples:**
- "You buy Organic Milk every 2 weeks at Farmers India ($11.99)"
- "Reminder: Time to restock — last purchased 13 days ago"
- "You haven't bought dog food in 25 days (usually every 3 weeks)"

**Why it matters:** Turns receipt data into a smart shopping assistant. Drives daily engagement.

**Effort:** ~2 days

---

### 8. Multi-Currency Support
**What:** Auto-detect currency from receipt and convert to user's home currency.
**Examples:**
- Receipt in € → auto-convert to USD at the date's exchange rate
- Travel dashboard: "Trip to Europe — $2,340 total across 18 receipts"

**Target users:** International travelers, expats, global shoppers.

**Effort:** ~2 days

---

### 9. Family/Household Sharing
**What:** Combine receipts from all family members into a shared household dashboard.
**Features:**
- Invite family members via email
- Shared dashboard: "Family grocery spend: $1,200 this month"
- Individual + combined views
- Privacy controls: choose what to share

**Why it matters:** Families need to track combined spending. No receipt app does this well.

**Effort:** ~4 days

---

### 10. Receipt Email Forwarding
**What:** Forward digital receipts (Amazon, Uber, etc.) to a dedicated email address.
**Flow:**
1. User gets email address: `satish@receipts.receiptvault.app`
2. Forward any receipt email to that address
3. Auto-parsed and added to their account — no scanning needed

**Why it matters:** Online purchases don't have paper receipts. This captures 100% of spending.

**Effort:** ~5 days (requires email processing backend)

---

## Tier 3 — Polish & Delight

### 11. Home Screen Widget
- Small widget: Monthly spending total
- Medium widget: Top 3 vendors this month
- Large widget: Spending by category chart

**Effort:** ~1 day

### 12. Apple Watch Companion
- Quick voice receipt entry from wrist
- Glance: today's spending total
- Complication: monthly budget remaining

**Effort:** ~3 days

### 13. Siri Shortcuts
- "Hey Siri, scan a receipt" → opens camera
- "Hey Siri, how much did I spend this month?" → speaks the total
- "Hey Siri, add a receipt for Starbucks $5.50" → voice entry

**Effort:** ~1 day

### 14. Charts & Visualizations
- Spending by category pie chart
- Monthly trend line chart
- Vendor comparison bar chart
- Year-over-year comparison

**Effort:** ~2 days (using Swift Charts)

### 15. CSV/PDF Data Export
- Export all receipts as CSV for spreadsheets
- Export formatted PDF report
- Share via email or AirDrop

**Effort:** ~1 day

---

## Recommended Build Order

### Phase 1: Retention & Revenue (Week 1-2)
| Priority | Feature | Impact | Effort |
|----------|---------|--------|--------|
| 1 | Warranty Tracker | Unique selling point | 2 days |
| 2 | Tax Categories | Revenue driver (Pro feature) | 1 day |
| 3 | Budget Alerts | User retention | 2 days |

### Phase 2: Growth (Week 3-4)
| Priority | Feature | Impact | Effort |
|----------|---------|--------|--------|
| 4 | Expense Reports | B2B appeal | 2 days |
| 5 | Price Comparison | Word-of-mouth | 3 days |
| 6 | Home Screen Widget | Daily engagement | 1 day |

### Phase 3: Expansion (Month 2)
| Priority | Feature | Impact | Effort |
|----------|---------|--------|--------|
| 7 | Split Receipt | Social/viral | 3 days |
| 8 | Recurring Purchases | Smart assistant | 2 days |
| 9 | Charts & Visualizations | Visual appeal | 2 days |
| 10 | CSV/PDF Export | Power users | 1 day |

### Phase 4: Platform (Month 3)
| Priority | Feature | Impact | Effort |
|----------|---------|--------|--------|
| 11 | Family Sharing | Household market | 4 days |
| 12 | Email Forwarding | 100% capture | 5 days |
| 13 | Apple Watch | Convenience | 3 days |
| 14 | Multi-Currency | International | 2 days |
| 15 | Siri Shortcuts | Integration | 1 day |

---

## Monetization Strategy

### Free Tier
- OCR-only receipt scanning (on-device)
- 5 receipts per month
- Basic dashboard
- Manual categorization

### Pro Tier ($4.99/month or $39.99/year)
- Claude AI parsing (perfect accuracy)
- Unlimited receipts
- Tax category auto-tagging
- Budget alerts
- Warranty tracker
- Expense report export
- Price comparison
- Priority support

### Business Tier ($9.99/month — future)
- Everything in Pro
- Family/team sharing (up to 5 members)
- Email forwarding
- Custom categories
- API access
- Multi-currency

---

## Competitive Landscape

| Feature | ReceiptVault | Expensify | Wave | Shoeboxed |
|---------|-------------|-----------|------|-----------|
| AI Receipt Parsing | ✅ Claude | ✅ | ❌ | ✅ |
| Voice Input | ✅ | ❌ | ❌ | ❌ |
| Warranty Tracker | ✅ | ❌ | ❌ | ❌ |
| Tax Auto-Categories | ✅ | ✅ | ✅ | ❌ |
| Price Comparison | ✅ | ❌ | ❌ | ❌ |
| Budget Alerts | ✅ | ❌ | ❌ | ❌ |
| Split Receipt | ✅ | ❌ | ❌ | ❌ |
| Free Tier | ✅ | Limited | ✅ | ❌ |
| Privacy (on-device OCR) | ✅ | ❌ | ❌ | ❌ |

**ReceiptVault's unique advantages:** Voice input, warranty tracking, price comparison, budget alerts, and on-device OCR for privacy. No competitor offers all of these.

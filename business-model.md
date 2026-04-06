# ReceiptVault — Business Model

## The Problem
Every household generates 50-100 receipts per month. Most get lost, making it impossible to:
- Track spending patterns
- Claim warranties when products break
- Organize tax deductions
- Split bills with friends
- Return items without receipts

## Revenue Model: Freemium SaaS

### Free Tier — $0/month
**Purpose:** Acquire users, demonstrate value

| Feature | Included |
|---------|----------|
| Receipt scanning (OCR) | 5 per month |
| Digital import | 5 per month |
| Voice recording | 5 per month |
| Basic dashboard | ✅ |
| Search | ✅ |
| Manual editing | ✅ |

**Why free works:** Users see the value immediately. The 5-receipt limit creates natural demand for Pro.

---

### Pro Tier — $4.99/month or $39.99/year
**Purpose:** Core revenue driver

| Feature | Included |
|---------|----------|
| Everything in Free | ✅ |
| Claude AI parsing (perfect accuracy) | ✅ Unlimited |
| Unlimited receipts | ✅ |
| Tax category auto-tagging | ✅ |
| Warranty tracker with reminders | ✅ |
| Budget alerts | ✅ |
| Price comparison | ✅ |
| Expense report export | ✅ |

**Your costs per Pro user:**
- Claude API: ~$0.50/month (avg 50 receipts × $0.01)
- Supabase: ~$0.10/month (storage + database)
- Total: ~$0.60/month

**Your profit per Pro user: ~$4.39/month ($52.68/year)**

---

### Business Tier — $9.99/month (Future)
**Purpose:** Higher ARPU from power users

| Feature | Included |
|---------|----------|
| Everything in Pro | ✅ |
| Family sharing (5 members) | ✅ |
| Email forwarding (auto-import) | ✅ |
| Custom categories | ✅ |
| Multi-currency | ✅ |
| Priority support | ✅ |

---

## Unit Economics

### Cost Structure
| Cost | Per User/Month | Notes |
|------|---------------|-------|
| Claude API | $0.50 | ~50 receipts × $0.01 (Haiku) |
| Supabase (DB) | $0.05 | Shared infrastructure |
| Supabase (Storage) | $0.05 | ~5MB images/month |
| Apple (30% cut) | $1.50 | On $4.99 subscription |
| **Total Cost** | **$2.10** | |
| **Revenue** | **$4.99** | |
| **Profit** | **$2.89/user/month** | **58% margin** |

### After Year 1 (Apple reduces to 15%)
| | Per User/Month |
|------|---------------|
| Apple (15% cut) | $0.75 |
| Other costs | $0.60 |
| **Total Cost** | **$1.35** |
| **Revenue** | **$4.99** |
| **Profit** | **$3.64/user/month** | **73% margin** |

---

## Revenue Projections

### Conservative Scenario
| Metric | Month 3 | Month 6 | Month 12 |
|--------|---------|---------|----------|
| Free users | 500 | 2,000 | 5,000 |
| Pro users (5% conversion) | 25 | 100 | 250 |
| Monthly revenue | $125 | $500 | $1,250 |
| Monthly costs | $53 | $210 | $525 |
| Monthly profit | $72 | $290 | $725 |
| **Annual profit** | | | **$8,700** |

### Moderate Scenario
| Metric | Month 3 | Month 6 | Month 12 |
|--------|---------|---------|----------|
| Free users | 2,000 | 10,000 | 30,000 |
| Pro users (7% conversion) | 140 | 700 | 2,100 |
| Monthly revenue | $700 | $3,500 | $10,500 |
| Monthly costs | $294 | $1,470 | $4,410 |
| Monthly profit | $406 | $2,030 | $6,090 |
| **Annual profit** | | | **$73,080** |

### Optimistic Scenario
| Metric | Month 3 | Month 6 | Month 12 |
|--------|---------|---------|----------|
| Free users | 10,000 | 50,000 | 200,000 |
| Pro users (10% conversion) | 1,000 | 5,000 | 20,000 |
| Monthly revenue | $5,000 | $25,000 | $100,000 |
| Monthly costs | $2,100 | $10,500 | $42,000 |
| Monthly profit | $2,900 | $14,500 | $58,000 |
| **Annual profit** | | | **$696,000** |

---

## Customer Acquisition Strategy

### Organic (Free)
1. **App Store Optimization** — keywords: receipt scanner, expense tracker
2. **Word of mouth** — "Split receipt" feature drives sharing
3. **Content marketing** — "5 ways to save on taxes with receipt tracking" blog posts
4. **Reddit/social** — r/personalfinance, r/frugal communities

### Paid (When profitable)
1. **Apple Search Ads** — target "receipt scanner" keyword (~$1-2 CPA)
2. **Social media** — Instagram/TikTok showing the scan-to-dashboard flow
3. **Influencer** — personal finance YouTubers

### Partnerships
1. **Accountants** — referral program for tax season
2. **Small businesses** — expense tracking for employees
3. **Coupon/rewards apps** — integration with receipt data

---

## Conversion Funnel

```
Download App (Free)
    ↓ 100%
Create Account
    ↓ 70%
Scan First Receipt (wow moment)
    ↓ 50%
Scan 5 Receipts (hit free limit)
    ↓ 30%
See "Upgrade to Pro" prompt
    ↓ 7-10%
Subscribe to Pro ($4.99/month)
    ↓ 80% retain month 2
    ↓ 60% retain month 6
    ↓ 40% retain month 12
```

**Key metric:** Time to "wow moment" — how fast can a user scan their first receipt and see it on the dashboard? Currently: **under 30 seconds**.

---

## Why This Business Model Works

1. **Low marginal cost** — Claude Haiku at $0.001/receipt means serving users is nearly free
2. **High switching cost** — once users have 100+ receipts stored, they won't switch
3. **Natural upgrade path** — free tier demonstrates value, limit creates urgency
4. **Recurring revenue** — subscriptions compound over time
5. **No hardware needed** — pure software, works on any iPhone
6. **Tax season spike** — annual predictable demand surge in Jan-Apr
7. **Warranty feature stickiness** — users NEED the app when products break (can't delete)

---

## Competitive Moat

1. **Claude AI + on-device OCR** — best-in-class accuracy with privacy
2. **Warranty tracking** — nobody else does this
3. **Price comparison** — unique data asset that grows with usage
4. **Voice input** — fastest receipt entry method
5. **Data network effect** — more receipts = better insights = more valuable app

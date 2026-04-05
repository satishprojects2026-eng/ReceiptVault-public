# Privacy Policy

**ReceiptVault**
**Last Updated:** April 5, 2026

## Introduction

ReceiptVault ("we", "our", "the app") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, and safeguard your information when you use our mobile application.

## Information We Collect

### Account Information
- Email address (for authentication)
- Display name (chosen by you)

### Receipt Data
- Receipt images captured via camera or imported from files
- Extracted receipt details: vendor name, date, item names, prices, subtotal, tax, total, payment method
- Voice recordings (processed on-device only, not stored as audio)

### Automatically Collected
- Device type and operating system version (for app compatibility)
- App usage analytics (crash reports via Apple)

## How We Process Your Data

### On-Device Processing
- **OCR (Optical Character Recognition):** Receipt images are processed entirely on your device using Apple Vision framework. No images are sent to external servers for text recognition.
- **Voice Recognition:** Speech-to-text processing occurs on your device using Apple Speech framework. Audio is not stored or transmitted.

### Cloud Storage
- Receipt data (text, amounts, dates) is stored in our secure cloud database (Supabase) to enable access across your devices.
- Receipt images are stored in secure cloud storage with signed, time-limited access URLs.
- All data is associated with your authenticated account and is not accessible to other users.

## Data Security

- All network communication uses HTTPS/TLS encryption
- Database access is protected by Row Level Security (RLS) — each user can only access their own data
- Receipt images are stored in private storage buckets with per-user access controls
- Authentication tokens are stored securely on your device
- The app requires biometric authentication (Face ID/Touch ID) or device passcode when returning from background
- File protection is enabled on all locally stored data

## Data Retention

- Your data is retained as long as your account is active
- When you delete your account, all associated receipt data, items, and images are permanently deleted
- We do not retain backups of deleted user data

## Your Rights

You have the right to:
- **Access** your data at any time through the app
- **Export** your receipt data
- **Correct** any inaccurate receipt information via the edit feature
- **Delete** your account and all associated data via Settings > Delete Account
- **Withdraw consent** by discontinuing use and deleting your account

## Third-Party Services

### Supabase
We use Supabase for authentication and data storage. Supabase processes data in accordance with their privacy policy: https://supabase.com/privacy

### Apple Services
- Apple Vision framework (on-device OCR)
- Apple Speech framework (on-device voice recognition)
- Apple App Store (distribution)

We do not sell, rent, or share your personal information with third parties for marketing purposes.

## Children's Privacy

ReceiptVault is not intended for use by children under 13. We do not knowingly collect personal information from children under 13.

## Changes to This Policy

We may update this Privacy Policy from time to time. We will notify you of any changes by posting the new Privacy Policy within the app and updating the "Last Updated" date.

## Contact Us

If you have any questions about this Privacy Policy, please contact us at:

Email: support@receiptvault.app

---

*This privacy policy is hosted at: https://satishprojects2026-eng.github.io/ReceiptVault/privacy-policy*

# ReceiptVault — App Store Submission Checklist

## Prerequisites
- [ ] Apple Developer Account ($99/year) — https://developer.apple.com
- [ ] App Store Connect access — https://appstoreconnect.apple.com

## App Store Connect Setup
1. Go to https://appstoreconnect.apple.com
2. Click **My Apps** → **+** → **New App**
3. Fill in:
   - Platform: **iOS**
   - Name: **ReceiptVault - Receipt Scanner**
   - Primary Language: **English (U.S.)**
   - Bundle ID: **com.satish.ReceiptVault**
   - SKU: **receiptvault-001**

## App Information
- Category: **Finance**
- Secondary Category: **Productivity**
- Content Rights: **Does not contain third-party content**
- Age Rating: **4+**

## Pricing
- Price: **Free**
- In-App Purchases: Set up later for Pro tier

## Version Information
### Description
Copy from: `AppStore/AppStoreMetadata.md`

### Keywords
```
receipt,scanner,expense,tracker,OCR,spending,budget,finance,organize,scan
```

### Support URL
```
https://satishprojects2026-eng.github.io/ReceiptVault-public/
```

### Privacy Policy URL
```
https://satishprojects2026-eng.github.io/ReceiptVault-public/privacy-policy
```

## Screenshots
Upload phone screenshots for **iPhone 6.7" Display** (iPhone 15 Pro Max / 16 Pro Max / 17 Pro Max):
1. Home screen (3 mode buttons)
2. Dashboard (month groups with vendors)
3. Vendor Detail (receipts by month)
4. Search results
5. Settings (Pro toggle)
6. Review screen (after scanning)

## App Review Information
### Contact Information
- First Name: Satish
- Last Name: [Your last name]
- Phone: [Your phone]
- Email: [Your email]

### Demo Account
- Email: test@receiptvault.app (or create a test account)
- Password: [test password]

### Notes for Reviewer
```
This app uses the device camera to scan paper receipts using Apple Vision
framework for on-device OCR text extraction. The Pro tier sends extracted
TEXT (not images) to an AI service for intelligent parsing. All data is
stored in a secure cloud database (Supabase) with row-level security.

To test:
1. Sign in with the demo account
2. Tap "Digital Receipt" → "Import File" → select any image
3. Review the parsed receipt data → "Confirm & Save"
4. Check Dashboard to see the saved receipt
5. Search by vendor name
6. Settings → Delete Account removes all data

The app requires camera, microphone, and speech recognition permissions
for the scan and voice features.
```

## Build & Upload
### From Xcode:
1. Select **Any iOS Device** as destination
2. **Product** → **Archive**
3. In Organizer window → **Distribute App**
4. Choose **App Store Connect**
5. Follow the upload wizard

### Or from command line:
```bash
# Create archive
xcodebuild -project ReceiptVault.xcodeproj -scheme ReceiptVault \
  -destination 'generic/platform=iOS' \
  -archivePath build/ReceiptVault.xcarchive archive

# Export for App Store
xcodebuild -exportArchive \
  -archivePath build/ReceiptVault.xcarchive \
  -exportPath build/export \
  -exportOptionsPlist ExportOptions.plist
```

## App Privacy (Data Collection)
In App Store Connect → App Privacy:

### Data Collected:
| Data Type | Collection | Linked to User | Tracking |
|-----------|-----------|----------------|----------|
| Email Address | Yes | Yes | No |
| Name | Yes | Yes | No |
| Photos | Yes | Yes | No |
| Financial Info (receipts) | Yes | Yes | No |

### Purpose:
- **Email/Name**: Account creation and authentication
- **Photos**: Receipt image capture and storage
- **Financial Info**: Receipt amounts, vendor names, spending tracking

### Data NOT collected:
- Location
- Health
- Browsing history
- Advertising data
- Diagnostics

## Post-Submission
- Apple review typically takes 24-48 hours
- If rejected, review the rejection reason and fix
- Common rejection reasons:
  - Missing privacy policy
  - Broken functionality
  - Placeholder content
  - Missing account deletion feature (we have this ✅)

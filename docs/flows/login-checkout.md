# Login & OTP Flow

This guide covers the WhatsApp authentication (OTP) process for users who are registered with FLIK or want to create an account during checkout.

## Overview

FLIK Checkout uses **WhatsApp OTP (One-Time Password)** authentication to enable quick and secure user verification. This method is:
- **Familiar**: Users already use WhatsApp
- **Fast**: No passwords to remember
- **Secure**: OTP verified through WhatsApp
- **Frictionless**: No account creation steps

**Target Users**:
- Registered FLIK users
- New users creating account during checkout
- Users preferring authentication over guest checkout

## Flow Diagram

```
Guest Checkout Page
    ↓
[Click "Login" Button]
    ↓
Login Page - Enter WhatsApp Number
    ↓
System sends OTP to WhatsApp
    ↓
User enters 6-digit OTP code
    ↓
Verification Successful?
├─→ YES: Existing Registered User?
│   ├─→ YES: Auto-filled Checkout Page (Desktop 3b/MWeb 3b)
│   └─→ NO: New User Profile Created
│
└─→ NO: Error Message, Retry
```

## Step-by-Step Walkthrough

### Step 1: Guest Checkout with Login Option

From the guest checkout entry point, user can choose to login instead of continuing as guest.

**Desktop View** (Standard Merchant):
![Desktop Guest Entry](../../assets/screenshots/guest-checkout/Desktop%20-%202.png)

**Mobile Web View** (Standard Merchant):
![Mobile Guest Entry](../../assets/screenshots/guest-checkout/MWeb%20-%202.png)

**Login Option**:
- **Left Section (Kontak)**: Shows "Informasi akun" (Account Information)
- **Login Link**: "Login" text link in top right
- **Registration Option**: Users can register through the login link

**User Action**: Clicks "Login" text button to access WhatsApp login

---

### Step 2: WhatsApp Login Page

User is presented with the login form asking for their WhatsApp phone number.

**Desktop View**:
![Desktop Login Page](../../assets/screenshots/login-flow/Desktop%20-%204.png)

**Mobile Web View**:
![Mobile Login Page](../../assets/screenshots/login-flow/MWeb%20-%204.png)

**Login Form Elements**:

#### Form Title:
- **"Masuk atau Daftar"** (Login or Register)
- **Subtitle**: "Masukkan nomor handphone kamu" (Enter your phone number)

#### Phone Number Input:
- **Country Code Selector**: Dropdown showing country flag (🇮🇩 Indonesia) with +62
- **Phone Number Field**: Text input with placeholder "Phone number"
- Flag shows current country is set to Indonesia (+62)

#### Action Button:
- **"Lanjutkan"** (Continue) - Primary button to proceed with OTP

#### Optional Actions:
- **"Kembali"** (Back) - Secondary button to return to previous screen

**Important Details**:
- Phone number must include country code
- System auto-selects Indonesia (+62) for Indonesian merchants
- User can change country if needed
- Phone number must be registered on WhatsApp

**User Action**: Enters phone number and clicks "Lanjutkan"

---

### Step 3: OTP Verification Page

After entering phone number, system sends OTP code to user's WhatsApp and displays verification page.

**Desktop View**:
![Desktop OTP Verification](../../assets/screenshots/login-flow/Desktop%20-%205.png)

**Mobile Web View**:
![Mobile OTP Verification](../../assets/screenshots/login-flow/MWeb%20-%205.png)

**OTP Page Elements**:

#### Phone Number Display:
- Shows the phone number at top: "+6285159852622"
- **"Ubah"** (Change) link to go back and modify phone number

#### OTP Verification Section:
- **Title**: "Verifikasi OTP"
- **Instructions**: "Masukkan kode OTP yang dikirim ke nomor WhatsApp" (Enter OTP code sent to WhatsApp number)

#### OTP Code Input:
- **Six digit input boxes**: User enters 6-digit code one digit per box
- Boxes highlight in blue as user types
- Auto-focus to next box after each digit

#### Countdown Timer:
- **Text**: "Mengirim kembali dalam 2 m 53 detik" (Resend in 2 m 53 seconds)
- Counts down from 2 minutes 53 seconds
- After timer expires, shows "Kirim Ulang" (Resend) button

#### Action Buttons:
- **"Kembali"** (Back) - Return to phone number entry
- **No explicit submit button** - System auto-verifies when all 6 digits entered

**System Behavior**:
- OTP sent immediately via WhatsApp
- User has limited time (usually 5-10 minutes) to enter code
- Code is case-sensitive if letters included (typically all numbers)
- Auto-verification triggers once all 6 digits filled
- If OTP incorrect, error message shown, user can retry
- "Kirim Ulang" button available after countdown expires to request new OTP

**User Action**: Receives WhatsApp message with OTP code, enters 6 digits

---

### Step 4A: Verification Success - Existing Registered User

If user is a registered FLIK user with existing data (address, payment method), system automatically logs them in and populates checkout page with saved information.

**Desktop View** (Auto-filled Checkout):
![Desktop Registered Checkout](../../assets/screenshots/registered-checkout/Desktop%20-%203b.png)

**Mobile Web View** (Auto-filled Checkout):
![Mobile Registered Checkout](../../assets/screenshots/registered-checkout/MWeb%20-%203b.png)

**What Appears**:

#### Contact Information (✅ Complete):
- Shows user's registered name: "Raam Pujangga Sadewa"
- Shows registered email: "raam1@flik.co.id"
- No changes needed
- Can be modified by clicking profile icon

#### Shipping & Payment (Auto-filled):

**Address** (✅ Auto-filled):
- Shows saved address: "Raam Pujangga Sadewa | +6281718544811"
- "Pusat Niaga Duta Mas Lt. 2 Blok E, No. 28 & 21, Jl. RS. Fatmawati Raya, RT.1/RW.5, C..."
- Click to change address or select from other saved addresses

**Courier** (✅ Auto-selected):
- Shows automatically selected cheapest courier: "SiCepat - Reguler ( Rp11,000 )"
- "Pengiriman ( 2 - 3 ) hari" (Delivery 2-3 days)
- Can be changed by clicking

**Payment Method** (✅ Default Selected):
- Shows QRIS as default payment method
- "Pay using QR code"
- Can be changed by clicking

#### Discount/Voucher Section:
- **Light blue box** with discount information
- "Ssst.. kamu bisa lebih hemat!" (Psst.. you can save more!)
- Can click to view and apply available discounts

#### Right Side Order Summary:
- Shows subtotal
- Shows shipping subtotal
- Shows total amount
- **"Bayar Sekarang"** (Pay Now) button - Ready to complete payment

**Important for Registered Users**:
- **QRIS default**: QRIS is the most used payment method for registered users
- **Courier auto-selected**: System chooses cheapest option automatically
- **Saved addresses**: All previous addresses available for selection
- **More discounts**: Registered users see MORE discount options than guest users

**User Action**: Reviews pre-filled information and can modify any field, then clicks "Bayar Sekarang"

---

### Step 4B: Verification Success - New User (First Time Registered)

If user is NOT in the system (new WhatsApp number), system creates new user profile but requires additional information before checkout can proceed.

**Expected Page**: Similar structure to guest checkout with all fields empty

**System Creates**:
- User account linked to WhatsApp number
- User profile with phone number
- Empty address and payment method fields

**User Must Complete**:
1. Full name (if not provided)
2. Email address
3. Shipping address
4. Payment method

**Same as Guest Checkout**: From this point, the flow is identical to guest checkout flow - user fills address, selects courier, chooses payment method, and completes payment.

**Key Difference**: Unlike guest users, this newly registered user's data will be saved for future purchases.

---

## Successful OTP Verification Scenarios

### Scenario A: Existing Registered User
1. Phone number exists in system
2. System verifies OTP
3. User automatically logged in
4. Checkout page pre-populated with saved data
5. User reviews and pays

### Scenario B: New User (First Time)
1. Phone number NOT in system
2. System verifies OTP and creates account
3. System redirects to checkout page (may require additional info)
4. User fills required information
5. User's data saved for future purchases

## OTP Best Practices

### For Users
- ✅ Check WhatsApp immediately after requesting OTP
- ✅ Enter OTP quickly before expiration (usually 5-10 minutes)
- ✅ Ensure correct phone number is entered
- ✅ If OTP not received, request a new one using "Kirim Ulang" button

### For Merchants
- ✅ Ensure WhatsApp integration is working
- ✅ Monitor OTP failure rates
- ✅ Provide clear instructions about WhatsApp requirement
- ✅ Have support process for users without WhatsApp

## Common Issues & Solutions

| Issue | Symptom | Solution |
|-------|---------|----------|
| OTP not received | No WhatsApp message after 1-2 minutes | Click "Kirim Ulang" (Resend) button, verify phone number is correct |
| Wrong OTP entered | Error message after submission | Check WhatsApp message for correct code, try again |
| OTP expired | Message says code is invalid | Use "Kirim Ulang" to request new OTP |
| Phone number error | Can't enter number correctly | Verify country code selected, check number format |
| User not registered after OTP | New user, no saved data | Fill checkout form completely, data saved for next purchase |
| Multiple accounts | Same number registered multiple times | Contact support to merge accounts |

## Security Considerations

### OTP Security
- **Time-limited**: OTP valid for 5-10 minutes only
- **Single-use**: Each OTP can only be used once
- **WhatsApp verified**: Only sent to verified WhatsApp accounts
- **Rate-limiting**: System prevents brute force attempts

### Data Protection
- Phone numbers encrypted in database
- OTP transmission via secure WhatsApp API
- User session tokens secured with expiration
- GDPR compliant data handling

## Login Flow Summary

| Step | Action | User Type | Result |
|------|--------|-----------|--------|
| 1 | Enter phone number | Any | OTP sent to WhatsApp |
| 2 | Enter OTP code | Any | Verification processed |
| 3 | System checks user status | Existing | Auto-fill checkout page |
| 3 | System checks user status | New | Create account, checkout form |
| 4 | Review/Complete | Existing | Skip to payment |
| 4 | Complete form | New | Fill address, courier, payment |
| 5 | Pay | Any | Transaction complete |

## Key Differences: Login vs. Guest Flow

| Aspect | Login Flow | Guest Flow |
|--------|-----------|-----------|
| **Authentication** | WhatsApp OTP | Direct name/email |
| **Data Persistence** | Saved across sessions | One-time only (guest) |
| **Future Purchases** | All data pre-filled | Must re-enter everything |
| **Discount Eligibility** | Full access to all discounts | Limited to some discounts |
| **Payment Methods** | Saved methods available | New payment each time |
| **Account Status** | Permanent account | Temporary guest session |

## Related Documentation

- [Guest Checkout Flow](./guest-checkout.md) - Compare with login flow
- [Registered User Checkout Flow](./registered-user-checkout.md) - Full registered experience
- [Address Management Feature](../features/address-management.md)
- [Payment Methods Feature](../features/payment-methods.md)

---

**Last Updated**: April 24, 2026  
**Version**: 1.0.0

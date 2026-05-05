# Guest Checkout Flow

This guide covers the complete guest checkout experience for users who are new to FLIK Checkout or do not have an active session.

## Overview

Guest checkout allows users to complete purchases without creating an account. They fill in their information once, and the system registers them as a guest checkout user in the database.

**Target Users**: 
- New customers visiting merchant website
- Existing registered users with expired FLIK Checkout sessions
- Users who prefer not to log in

## Flow Diagram

```
Merchant Website (with items)
    ↓
[Click FLIK Button]
    ↓
Entry Point
    ↓
[No Active Session]
    ↓
Choose Path:
├─→ [Continue as Guest]
│   ↓
│   Fill Name & Email (Modal)
│   ↓
│   Guest Account Created
│   ↓
│   Fill Missing Info (Address, Courier, Payment)
│
└─→ [Login with WhatsApp]
    (See Login Flow documentation)
```

## Step-by-Step Walkthrough

### Step 1: Entry Point

User arrives at the merchant's product page and sees the FLIK button at the bottom right with promotional messaging.

**Desktop View**:
![Desktop Entry Point](../../assets/screenshots/entry-point/Desktop%20-%201.png)

**Mobile Web View**:
![Mobile Entry Point](../../assets/screenshots/entry-point/MWeb%20-%201.png)

**What User Sees**:
- Product information (name, price, specifications)
- Product image
- "Add to cart" button (merchant's default)
- **FLIK "Buy it now" button** (prominent black button with orange FLIK logo)

**User Action**: Clicks the FLIK "Buy it now" button

---

### Step 2: FLIK Checkout Entry (No Active Session)

System checks if user has an active FLIK Checkout session. Since this is a new/guest user, no session exists.

The user is presented with two options:
1. **Login with WhatsApp** - For existing registered users
2. **Continue as Guest** - For new or non-registered users

**Desktop View** (Standard Merchant - No Pickup):
![Desktop Guest Entry](../../assets/screenshots/guest-checkout/Desktop%20-%202.png)

**Desktop View** (Merchant with Pickup Feature):
![Desktop with Pickup](../../assets/screenshots/entry-point/Desktop%20-%202b.png)

**Mobile Web View** (Standard Merchant):
![Mobile Guest Entry](../../assets/screenshots/guest-checkout/MWeb%20-%202.png)

**Key Elements**:
- **Left Section (Kontak - Contact)**:
  - "Informasi akun" (Account Information) - Shows login/register link
  - Red text: "Lengkapi data akun" (Complete account data)
- **Right Section (Ringkasan Belanja - Order Summary)**:
  - Shows subtotal: Rp199,000 (example)
  - Shows total: Rp199,000
- **Pengiriman & Pembayaran** (Shipping & Payment):
  - ⚠️ Alamat Pengiriman (Delivery Address) - Incomplete (red text)
  - ⚠️ Pilih Kurir (Select Courier) - Incomplete (red text: "Kurir belum tersedia, ganti atau pilih alamat")
  - ⚠️ Metode Pembayaran (Payment Method) - Incomplete (red text: "Silhakan pilih metode pembayaran")
  - **Diskon** (Discount) - Optional section showing potential discounts

**For Merchants with Store Pickup Feature** (Desktop 2b):
- **Top Tab Interface**:
  - "Kirim ke rumah" (Ship to home) - Default selected
  - "Ambil di toko" (Pick up in store) - Alternative option

**User Action**: Clicks on "Informasi akun" (Account Information) section or any unfilled field to proceed

---

### Step 3: Guest Information Modal

When user clicks on any information field or section, a modal appears asking for basic information to register as a guest checkout user.

**Desktop View**:
![Desktop Guest Info Modal](../../assets/screenshots/guest-checkout/Desktop%20-%203.png)

**Mobile Web View**:
![Mobile Guest Info Modal](../../assets/screenshots/guest-checkout/MWeb%20-%203.png)

**Modal Fields**:
- **Email** (Required): User's email address for transaction notifications
- **Nama Lengkap** (Full Name) (Required): User's full name
- **Simpan** (Save) Button: Primary action to create guest account

**System Behavior**:
- Modal forces user to fill these two fields before proceeding
- Email and name are mandatory
- Once submitted, the system:
  1. Creates a guest checkout user profile
  2. Assigns session token
  3. Registers email for transaction notifications

**User Action**: Fills in email and name, clicks "Simpan" button

---

### Step 4: Incomplete Checkout Page

After email and name are saved, the user is shown the checkout page with remaining required fields highlighted.

**Desktop View**:
![Desktop Incomplete Checkout](../../assets/screenshots/guest-checkout/Desktop%20-%203a.png)

**Mobile Web View**:
![Mobile Incomplete Checkout](../../assets/screenshots/guest-checkout/MWeb%20-%203a.png)

**Current State**:
- **Kontak (Contact)**: ✅ Completed
  - "Informasi akun" now shows the user's name
  - Displays email (in gray, read-only)
- **Pengiriman & Pembayaran** (Shipping & Payment): ❌ Incomplete

**Required Information Still Needed**:
1. ⚠️ **Alamat Pengiriman** (Delivery Address) - Red text: "Masukkan alamat pengiriman"
2. ⚠️ **Pilih Kurir** (Select Courier) - Red text: "Kurir belum tersedia, ganti atau pilih alamat"
3. ⚠️ **Metode Pembayaran** (Payment Method) - Red text: "Silhakan pilih metode pembayaran"

**Optional**:
- **Diskon** (Discount) - Light blue section, optional to add discount

**Item Display** (Right section):
- Shows order summary with item details
- Displays merchant name and location
- Shows item price and quantity

**User Action**: Clicks on "Alamat Pengiriman" to add shipping address

---

### Step 5: Address Entry with Map

User is presented with a modal to enter their delivery address. The system includes:
- Recipient details (name, phone)
- Address search field
- Interactive map for location selection
- Address details form
- Auto-fill options

**Desktop View**:
![Desktop Address Modal](../../assets/screenshots/features/Desktop%20-%206.png)

**Mobile Web View**:
![Mobile Address Modal](../../assets/screenshots/features/MWeb%20-%206.png)

**Modal Sections**:

#### Error Validation (shown only if validation fails):
- Red box: "Isi Nomor Handphone yang valid" (Enter valid phone number)

#### Recipient Details:
- **Nama Penerima** (Recipient Name): Pre-filled with guest's name, editable
- **HP Penerima** (Recipient Phone): Requires Indonesia phone code (+62), editable

#### Address Location:
- **Search Field**: "Type Location, Place, Apartment, Building" - To search address
- **Interactive Map**: Shows current location with red marker
- **Drag Instructions**: "Drag marker atau cari alamat" (Drag marker or search address)
- **View on Map**: "Lihat di maps" (View on maps) link

#### Address Details:
- **Alamat** (Address): Full address text area
- **Detail Alamat** (Address Details): Additional info (Gedung, Lantai, RT/RW, etc.)
- **Autofill**: Dropdown (optional auto-fill)
- **Kode Pos** (Postal Code): Zip code input

#### Action Button:
- **Simpan** (Save) Button: Saves address and returns to checkout page

**System Behavior**:
- Validates phone number format (must be valid)
- Validates address against service coverage areas
- Checks if address is in "red zone" (restricted areas)
- If red zone, shows additional shipping costs

**User Action**: Fills in all address information and clicks "Simpan"

---

### Step 6: Address Saved & Courier Auto-Selection

After address is saved, the system automatically selects the most cost-effective courier and returns user to the checkout page.

**Desktop View**:
![Desktop Courier Auto-Selected](../../assets/screenshots/guest-checkout/Desktop%20-%208.png)

**Mobile Web View**:
![Mobile Courier Auto-Selected](../../assets/screenshots/guest-checkout/MWeb%20-%208.png)

**What Changed**:
- ✅ **Alamat Pengiriman**: Now shows the saved address with user's phone number
- ✅ **Pilih Kurir**: Now shows auto-selected courier (cheapest option)
  - Example: "SiCepat - Regular ( Rp11,000 )" 
  - Shows shipping duration: "Pengiriman ( 2 - 3 ) hari"
- ❌ **Metode Pembayaran**: Still required (red text)

**Courier Information Displayed**:
- Courier logo/icon
- Courier name and service type
- Price in Rupiah
- Estimated delivery duration (2-3 days)

**Note on Auto-Selection**:
- System chooses the "Ongkos Kirim Termurah" (cheapest shipping option)
- User can click to see alternatives and select different courier
- More details: See [Courier Selection Feature Documentation](../features/courier-selection.md)

**Discount Section**:
- Light blue box showing optional discount application
- "Ssst.. kamu bisa lebih hemat!" (Psst.. you can save more!)
- User can click to view available discounts

**User Action**: Clicks on "Metode Pembayaran" to select payment method

---

### Step 7: Payment Method Selection

User sees all available payment methods organized by category. Payment options vary based on merchant configuration.

**Desktop View**:
![Desktop Payment Methods](../../assets/screenshots/features/Desktop%20-%2010.png)

**Mobile Web View**:
![Mobile Payment Methods](../../assets/screenshots/features/MWeb%20-%2010.png)

**Payment Categories**:

#### E-Wallets:
- OVO - "Pay using OVO" (with "Lanjutkan" button to connect)
- ShopeePay - "Pay using ShopeePay"
- Dana - "Pay using Dana"
- GoPay - "Pay using GoPay"

#### QRIS:
- QRIS - "Pay using QR code" (Radio button, unselected by default)

#### Virtual Accounts (Rekening Virtual):
- BCA VA - "Pay using BCA Virtual Account"
- MANDIRI VA - "Pay using MANDIRI Virtual Account"
- BNI VA - "Pay using BNI Virtual Account"
- BRI VA - "Pay using BRI Virtual Account"
- PERMATA VA - "Pay using PERMATA Virtual Account"
- BSI VA - "Pay using BSI Virtual Account"

**User Action**: Selects a payment method (e.g., clicks "Lanjutkan" for wallet or clicks radio button for bank option)

---

### Step 8: Payment Method Confirmed

After selecting a payment method, user returns to the checkout page with payment method confirmed.

**Desktop View**:
![Desktop Payment Confirmed](../../assets/screenshots/guest-checkout/Desktop%20-%208a.png)

**Mobile Web View**:
![Mobile Payment Confirmed](../../assets/screenshots/guest-checkout/MWeb%20-%208a.png)

**Checkout Status**:
- ✅ **Kontak** (Contact): Complete - Shows user name
- ✅ **Alamat Pengiriman** (Address): Complete - Shows full address with phone
- ✅ **Pilih Kurir** (Courier): Complete - Shows selected courier and cost
- ✅ **Metode Pembayaran** (Payment Method): Complete - Shows selected payment method
- ✅ **Diskon** (Discount): Optional - Can still be modified

**Right Side Summary**:
- **Subtotal**: Rp143,000
- **Subtotal Pengiriman** (Shipping Subtotal): Rp11,000
- **Total**: Rp154,000

**Action Button**:
- **Bayar Sekarang** (Pay Now) - Primary button, enabled and ready to complete purchase

**User Action**: Reviews all information and clicks "Bayar Sekarang" (Pay Now)

---

### Step 9: Discount Application (Optional)

If user chooses to apply a discount before payment, they can click the "Diskon" section.

**Desktop View** (Guest User Discounts):
![Desktop Guest Discounts](../../assets/screenshots/features/Desktop%20-%2011b.png)

**Mobile Web View** (Guest User Discounts):
![Mobile Guest Discounts](../../assets/screenshots/features/MWeb%20-%2011b.png)

**Discount Modal**:

#### Voucher Code Input:
- Text input field: "Masukkan kode voucher disini" (Enter voucher code here)
- **Terapkan** (Apply) button

#### Applied Promotions:
- Shows currently applied promotions (example: "ZMNOW SHIPPING")
- Checkmark icon indicates active promotion

#### Available Reward Programs:
- **Reward** section showing:
  - Merchant-specific rewards (e.g., "ZMNow Saldo: Rp0")
  - FLIK Rewards (e.g., "FLIK Reward Saldo: Rp0")
  - Applicability notes (e.g., "Applicable: Rp0")

#### FLIK Vouchers:
- Multiple voucher options from FLIK
- Examples:
  - "FLIKIS - Discount 15K"
  - "WEBSALE30AGS_OVERLIMIT - Discount 30K, Min. pembelian Rp1,000"
- Plus icon (+) to add voucher

#### Merchant Vouchers:
- Merchant-specific discounts
- May have restrictions for guest users
- Plus icon (+) to add voucher

**Important Note for Guests**:
- Guest users see LIMITED discount options
- Some merchant vouchers may be restricted to registered users only
- FLIK system vouchers are generally available to all users

**User Action**: Enters voucher code or clicks plus icon to apply discount, clicks "Terapkan" button

---

### Step 10: Payment Gateway

After clicking "Bayar Sekarang", user is redirected to the payment gateway page specific to their selected payment method.

**Desktop View** (QRIS Example):
![Desktop Payment Gateway](../../assets/screenshots/guest-checkout/Desktop%20-%2012.png)

**Mobile Web View** (QRIS Example):
![Mobile Payment Gateway](../../assets/screenshots/guest-checkout/MWeb%20-%2012.png)

**Payment Page Elements**:

#### Transaction Details:
- **ID Transaksi** (Transaction ID): Unique identifier (e.g., "23042026-DIVUXH")
- **Batas Pembayaran** (Payment Deadline): Date and time (e.g., "Kamis, 23 April 2026 19:45")
- **Total Pembayaran** (Total Payment): Amount due (e.g., "Rp154.000")

#### Payment Method (QRIS Example):
- Large QRIS code image for scanning
- **Scan untuk bayar** (Scan to pay) instruction
- **DOWNLOAD QRIS** link to save QR code

#### Payment Instructions:
- **Cara bayar** (How to Pay) - Expandable sections for each payment method:
  - **GoPay**: Step-by-step instructions
  - **ShopeePay**: Step-by-step instructions
  - **DANA**: Step-by-step instructions
  - **Bank Mandiri**: Instructions for bank transfer
  - **Bank BCA**: Instructions for bank transfer
  - **Bank BNI**: Instructions for bank transfer
  - **Bank Jenius**: Instructions for bank transfer

#### Return Action:
- **Kembali ke merchant** (Return to merchant) button - Returns to merchant site after payment

**System Behavior**:
- Payment gateway confirms transaction with payment provider
- Upon successful payment, transaction is recorded
- User receives email confirmation at registered email address
- User can view transaction status on merchant site

**User Action**: Completes payment via their selected method

---

## Guest Checkout Summary

| Step | Action | Status |
|------|--------|--------|
| 1 | Click FLIK Button | Guest user identified |
| 2 | Choose Guest Checkout | Entry to checkout |
| 3 | Enter Name & Email | Guest account created |
| 4 | Review Required Info | Fields identified |
| 5 | Enter Address | Address saved, courier auto-selected |
| 6 | Select Payment Method | Payment method confirmed |
| 7 | (Optional) Apply Discount | Discount applied |
| 8 | Review & Pay | Payment initiated |
| 9 | Complete Payment | Transaction complete |

## Key Differences: Guest vs. Registered Users

| Feature | Guest User | Registered User |
|---------|-----------|-----------------|
| **Registration** | Instant guest account | Full account with history |
| **Address Options** | Add new address only | Add new + select from saved |
| **Available Discounts** | Limited selection | Full selection + personalized |
| **Rewards Eligibility** | No rewards | Eligible for rewards program |
| **Pre-filled Data** | None | Address, payment method auto-filled |
| **Courier Selection** | Manual + auto cheapest | Same auto-selection |
| **Payment Methods** | All available | All available + saved methods |

## Best Practices for Guests

1. **Keep it simple**: Minimize required fields
2. **Provide clear instructions**: Address entry can be confusing
3. **Show what's happening**: Display progress indicators
4. **Make discounts visible**: Highlight available savings
5. **Confirm before payment**: Allow user to review all details

## Common Issues & Solutions

| Issue | Cause | Solution |
|-------|-------|----------|
| Address not found | Invalid address format | Use map to pinpoint location |
| Red zone address | Area has restricted delivery | Accept surcharge or select different address |
| Courier unavailable | No carriers serve area | Change address or contact support |
| Payment failed | Payment provider issue | Retry with same method or try different method |
| Email not received | Email filtering | Check spam folder or update email |

## Related Documentation

- [Address Management Feature](../features/address-management.md)
- [Courier Selection Feature](../features/courier-selection.md)
- [Payment Methods Feature](../features/payment-methods.md)
- [Discounts & Vouchers Feature](../features/discounts-vouchers.md)
- [Login & OTP Flow](./login-checkout.md)

---

**Last Updated**: April 24, 2026  
**Version**: 1.0.0

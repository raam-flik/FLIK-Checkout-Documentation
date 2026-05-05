# Registered User Checkout Flow

This guide covers the checkout experience for users who are registered with FLIK and have an active session with saved data.

## Overview

**Registered User Checkout** offers the fastest, most frictionless experience. Users benefit from:
- **One-Click**: Saved address and payment method
- **Auto-Selection**: Cheapest courier selected automatically
- **Personalized**: Access to all available discounts and rewards
- **Streamlined**: Minimal steps to complete purchase

**Target Users**:
- Users logged in via WhatsApp with active FLIK session
- Users with previously saved information
- Returning customers

## Session Requirements

For a user to get the registered checkout experience:
1. ✅ Successfully logged in via WhatsApp OTP
2. ✅ Account exists in FLIK system with saved data
3. ✅ Session token is valid (not expired)
4. ✅ Browser/app has stored session cookie

If any requirement fails, user falls back to guest checkout or must re-login.

## Flow Diagram

```
Merchant Website (with items)
    ↓
[Click FLIK Button]
    ↓
System checks session
    ↓
✅ Active Session Found
    ↓
Display Registered User Checkout
    ↓
Auto-filled Information:
├─ Address (from saved)
├─ Courier (cheapest auto-selected)
├─ Payment Method (QRIS default)
└─ Discounts/Rewards (all available)
    ↓
[Review & Modify if Needed]
    ↓
[Click "Bayar Sekarang" (Pay Now)]
    ↓
Payment Gateway
    ↓
Transaction Complete
```

## Step-by-Step Walkthrough

### Step 1: Entry Point - Automatic Detection

When a registered user with active session clicks the FLIK button, the system automatically detects their logged-in status and bypasses login/guest choice screens.

**No Login Modal**: Registered users skip directly to checkout page.

**System Checks**:
- ✅ Session token validity
- ✅ User account exists
- ✅ Saved address available
- ✅ Previous payment methods stored

---

### Step 2: Registered User Checkout Page - Complete & Auto-Filled

Registered users see a fully prepared checkout page with all information already filled in from their saved data.

**Desktop View**:
![Desktop Registered Checkout](../../assets/screenshots/registered-checkout/Desktop%20-%203b.png)

**Mobile Web View**:
![Mobile Registered Checkout](../../assets/screenshots/registered-checkout/MWeb%20-%203b.png)

**Kontak (Contact) Section** - ✅ Complete:
- Shows user's registered name: "Raam Pujangga Sadewa"
- Shows registered email: "raam1@flik.co.id"
- Not editable by default but can click to modify
- User can update profile information if needed

**Pengiriman & Pembayaran (Shipping & Payment) Section**:

#### Address (✅ Auto-filled):
- **Status**: Complete with primary saved address
- **Display Format**: "Name | Phone Number" + Full Address
- **Example**: "Raam Pujangga Sadewa | +6281718544811"
- **Address Details**: "Pusat Niaga Duta Mas Lt. 2 Blok E, No. 28 & 21, Jl. RS. Fatmawati Raya, RT.1/RW.5, C..."
- **User Can**: Click to select different address or add new address
- **Feature**: See [Address Management](../features/address-management.md)

#### Courier (✅ Auto-selected):
- **Status**: Pre-selected (cheapest option)
- **Display**: "SiCepat - Reguler ( Rp11,000 )"
- **Delivery Time**: "Pengiriman ( 2 - 3 ) hari" (Delivery 2-3 days)
- **User Can**: Click to see alternatives and select different courier
- **Auto-Selection Logic**: System chooses minimum shipping cost by default
- **Feature**: See [Courier Selection](../features/courier-selection.md)

#### Payment Method (✅ Default Selected - QRIS):
- **Status**: QRIS selected as default
- **Display**: "Silhakan pilih metode pembayaran" becomes actual method
- **QRIS Details**: "Pay using QR code"
- **Why QRIS Default**: Highest transaction volume for registered users
- **User Can**: Click to select different payment method
- **Available Methods**: All payment methods merchant supports
- **Feature**: See [Payment Methods](../features/payment-methods.md)

#### Discount/Voucher Section - Optional:
- **Status**: Light blue information box
- **Message**: "Ssst.. kamu bisa lebih hemat!" (Psst.. you can save more!)
- **User Can**: Click to view all available discounts and vouchers
- **Available To Registered**: Full selection of:
  - FLIK system vouchers
  - Merchant-specific vouchers (available to registered users)
  - Reward programs
- **Feature**: See [Discounts & Vouchers](../features/discounts-vouchers.md)

#### Additional Features for Registered Users:
- **Potential Reward Section**: Shows estimated rewards/cashback from transaction
- **Loyalty Points**: May display points earned from purchase
- **Subscription Benefits**: If user has active subscription, show benefits

**Order Summary (Right Panel)**:
- **Subtotal**: Item total (e.g., Rp143,000)
- **Subtotal Pengiriman**: Shipping cost (e.g., Rp11,000)
- **Total**: Grand total (e.g., Rp154,000)
- **"Bayar Sekarang"** Button: Enabled and ready

---

### Step 3: Optional - View/Modify Profile

Registered users can click on the profile section to view or update their account information.

**Profile Icon**: Click the user icon in top right corner

**Expected Behavior**:
- Show registered user's name
- Option to view/edit profile details
- Option to logout
- Quick links to account settings

**User Action**: (Optional) Clicks profile icon or proceeds directly to payment

---

### Step 4: Optional - Select Different Address

If user wants to use a different address (not the primary saved one), they click on the address section.

**Address Selection Modal**:
Shows list of previously saved addresses with ability to select or add new one.

**Desktop View** (Address List):
![Desktop Saved Addresses](../../assets/screenshots/features/Desktop%20-%209.png)

**Mobile Web View** (Saved Addresses):
![Mobile Saved Addresses](../../assets/screenshots/features/MWeb%20-%209.png)

**Modal Contents**:

#### Title:
- **"Alamat Pengiriman"** (Delivery Address)
- **Helper Text**: "Centang alamat sebagai default" (Check address as default)

#### Address List:
- **Each Address Shows**:
  - Address label (if given): e.g., "Tukla Kuy | +62851..." 
  - Full address text
  - Edit/Delete buttons (Ubah, Hapus)
  - Default indicator (radio button or checkmark)

- **Primary Address** (marked with checkmark):
  - "Tukla Kuy | +62851598852622"
  - "Tukla Kuy | +62851598852622"
  - "Kosan Pakde, Jl. Kebagusan I No.1 2, RT.2/RW.4, Kebagusan, Ps. Minggu, Kota Jakarta Selatan, Daerah Khusus Ibukota Jakarta 12520, Indonesia"

- **Secondary Address**:
  - "Tukla Kuy | +62851598852622"
  - "Kosan Pakde, Jl. Kebagusan I No.1 2, RT.2/RW.4, Kebagusan, Ps. Minggu, Kota Jakarta Selatan, Daerah Khusus Ibukota Jakarta 12520, Indonesia"
  - Can be selected to make primary

#### Add New Address:
- **Button**: "+ Tambah Alamat" (Add Address)
- **Opens**: Same address entry modal as guest checkout (see Guest Checkout Step 5)
- **Same Fields**: Recipient name, phone, address search, map, address details

#### Action:
- **Ubah** (Edit): Modify existing address
- **Hapus** (Delete): Remove address from saved list
- **Select**: Click address or radio button to select as current shipping address

**User Action**: Selects alternate address or adds new address, confirms selection

---

### Step 5: Optional - Select Different Courier

If user wants to see courier alternatives (faster delivery or different carrier), they click on the courier section.

**Courier Selection Modal**:

**Desktop View** (Courier Options):
![Desktop Courier Selection](../../assets/screenshots/features/Desktop%20-%2011.png)

**Mobile Web View** (Courier Options):
![Mobile Courier Selection](../../assets/screenshots/features/MWeb%20-%2011.png)

**Modal Contents**:

#### Title:
- **"Pilih Kurir"** (Select Courier)

#### Courier Options Listed:
Each courier shows:
- **Courier Logo/Icon**: Visual identifier
- **Courier Name**: e.g., "Gojek - Same Day"
- **Pricing**: e.g., "( Rp36,500 Rp26,500 )" - Original price crossed out, sale price shown
- **Delivery Time**: e.g., "Pengiriman ( 6 - 8 ) jam" (Delivery 6-8 hours)
- **Radio Button**: For selection

#### Available Couriers (Example List):
1. **Gojek - Same Day** - Rp26,500 (from Rp36,500) - 6-8 hours
2. **Gojek - Instant** - Rp50,000 (from Rp60,000) - 1-3 hours  
3. **Grab - Instant** - Rp52,000 (from Rp62,000) - 1-3 hours
4. **Grab - Same Day** - Rp17,000 (from Rp27,000) - 6-8 hours
5. **J&T - EZ** - GRATIS (Free) - 3-4 hari (days)
6. **SiCepat - Regular** - GRATIS (Free) - 2-3 days - **✅ Currently Selected**

#### Selection:
- **Currently Selected**: "SiCepat - Regular" shown with blue checkmark
- **User Selects**: Clicks radio button next to desired courier
- **Selection Updates**: Shipping cost and delivery time update automatically
- **Confirm**: Click same button or auto-confirm on selection

**Cost Variations**:
- **Express Options**: Higher cost, faster delivery (same-day or 1-3 hours)
- **Standard Options**: Lower cost, normal delivery (2-5 days)
- **Free Shipping**: Some couriers show GRATIS (free) option

**User Action**: Clicks radio button for preferred courier, confirms selection

---

### Step 6: Optional - Select Different Payment Method

If user wants to change from QRIS to another payment method, they click on the payment section.

**Payment Selection Modal**:

**Desktop View** (Payment Methods):
![Desktop Payment Methods](../../assets/screenshots/features/Desktop%20-%2010.png)

**Mobile Web View** (Payment Methods):
![Mobile Payment Methods](../../assets/screenshots/features/MWeb%20-%2010.png)

**Same as Guest Checkout**: Payment method selection is identical
- E-wallets (OVO, ShopeePay, Dana, GoPay)
- QRIS
- Virtual Accounts (BCA, MANDIRI, BNI, BRI, PERMATA, BSI)

**Difference for Registered Users**:
- ✅ May see **Saved Payment Methods** in addition to new options
- ✅ Can quickly select previously used payment methods
- ✅ Option to save new payment method for future use

**User Action**: Selects preferred payment method, confirms selection

---

### Step 7: Optional - View Available Discounts

Registered users have access to more discount options. They can click the discount section to see all available deals.

**Discount/Voucher Modal**:

**Desktop View** (Registered User Discounts):
![Desktop Registered Discounts](../../assets/screenshots/features/Desktop%20-%2011a.png)

**Mobile Web View** (Registered Discounts):
![Mobile Registered Discounts](../../assets/screenshots/features/MWeb%20-%2011a.png)

**Key Differences from Guest Discounts**:

#### More Voucher Options:
- **FLIK System Vouchers**: Full collection available
  - FLIK5 - Discount 5K
  - BTWHG - Discount 20%
  - BTWHG_AUG_EXPIRED - Discount 10K (expired)
  - WEBSALE30AGS_OVERLIMIT - Discount 30K (with min. Rp1,000)

#### Reward Programs:
- **Merchant-Specific Rewards**: Visible for registered users
- **FLIK Reward**: Access to FLIK loyalty points
- **Cashback Programs**: Earn cashback on purchases

#### Actions:
- **Plus Icon** (+): Add available voucher
- **Terapkan** (Apply): Apply selected discount
- **Each Discount Shows**: Code, discount amount, minimum purchase requirements, expiration date

#### Advantages Over Guest:
- ✅ Can see merchant-specific vouchers (may be restricted to registered only)
- ✅ Access to loyalty points and rewards
- ✅ Personalized discount suggestions based on purchase history
- ✅ Historical discount usage tracking

**Feature**: See [Discounts & Vouchers](../features/discounts-vouchers.md)

**User Action**: Selects and applies desired discount, confirms

---

### Step 8: Exclusive - View Rewards Information

Registered users can click the rewards info icon to understand what rewards they'll earn from this purchase.

**Rewards Info Popup**:

**Desktop/Mobile View**:
![Rewards Info Popup](../../assets/screenshots/features/Desktop%20-%207.png)

**Popup Contents**:

#### Title:
- **"Potensi Reward"** (Potential Reward)

#### Message:
- **"Belanja terus, tetap hemat!"** (Keep shopping, save more!)
- **"Nikmati reward merchant hingga Rp9.950"** (Enjoy merchant rewards up to Rp9,950)

#### Explanation:
- **Main Text**: "Cashback Rp9.950 Merchant Reward akan kamu terima setelah transaksi selesai" (You'll receive Rp9,950 Merchant Reward cashback after transaction completes)

#### How to Earn Rewards:
- **"Cara dapat Merchant Reward:"** (How to earn Merchant Rewards)
  1. "Beli produk dari merchant FLIK Partners" (Buy products from FLIK Partner merchants)
  2. "Setelah transaksi selesai, kamu akan dapat Merchant Reward" (After transaction completes, you'll get Merchant Reward)
  3. "Gunakan Merchant Reward untuk transaksi selanjutnya" (Use Merchant Reward for next transactions)

#### Close Button:
- **"Tutup"** (Close) button to dismiss popup

**Benefit for Registered Users**:
- ✅ See estimated reward amount before purchasing
- ✅ Understand how rewards program works
- ✅ Encourages loyalty program participation
- ✅ Transparent breakdown of benefits

**Feature**: See [Rewards System](../features/rewards.md)

**User Action**: Reads reward information, clicks "Tutup" to close

---

### Step 9: Review Complete Checkout Information

After any optional modifications, user reviews the complete checkout page before final payment.

**Final Checkout State**:
All sections show complete and correct information:
- ✅ **Contact**: Registered user name and email
- ✅ **Address**: Selected delivery address with full details
- ✅ **Courier**: Selected courier with delivery time and cost
- ✅ **Payment Method**: Selected payment method ready
- ✅ **Discounts**: Any applied discounts shown in summary
- ✅ **Order Total**: Final amount with all adjustments

**Order Summary**:
- Shows itemized subtotal
- Shows shipping subtotal
- Shows any discount reductions
- **Shows grand total** ready for payment

**Final Button**:
- **"Bayar Sekarang"** (Pay Now) - Ready to proceed to payment gateway

**User Action**: Reviews all information, confirms accuracy, clicks "Bayar Sekarang"

---

### Step 10: Payment Processing

After clicking "Bayar Sekarang", system processes payment through selected payment gateway (identical to guest checkout).

**Payment Gateway Page**:

**Desktop View** (QRIS Example):
![Desktop Payment Gateway](../../assets/screenshots/guest-checkout/Desktop%20-%2012.png)

**Mobile Web View** (QRIS Example):
![Mobile Payment Gateway](../../assets/screenshots/guest-checkout/MWeb%20-%2012.png)

**Same as Guest Checkout Process**:
- Transaction ID generated
- Payment deadline shown
- Payment instructions displayed
- User completes payment through chosen method
- Confirmation sent to registered email

**Post-Payment**:
- ✅ Merchant receives order
- ✅ User's FLIK profile updated with purchase history
- ✅ Rewards/cashback credited to account
- ✅ Address marked as recently used
- ✅ Transaction record saved in user's history

---

## Registered User Advantages

| Feature | Guest | Registered |
|---------|-------|-----------|
| **Entry Speed** | Multiple screens | Instant checkout |
| **Saved Data** | None | Address, payment method |
| **Courier Selection** | Auto cheapest | Auto cheapest, can change |
| **Available Discounts** | Limited | Full access |
| **Reward Program** | Not eligible | Full access |
| **Payment Options** | All | All + saved methods |
| **Purchase History** | Not saved | Permanently saved |
| **Future Checkouts** | Re-enter everything | Pre-filled data |

## Registered User Checkout Summary

| Step | Action | Required? | Time |
|------|--------|-----------|------|
| 1 | System detects session | Auto | Instant |
| 2 | Auto-fill checkout data | Auto | Instant |
| 3 | Review information | No | 5-10 sec |
| 4 | Modify address (optional) | No | 30-60 sec |
| 5 | Change courier (optional) | No | 15-30 sec |
| 6 | Change payment (optional) | No | 15-30 sec |
| 7 | View discounts (optional) | No | 30-60 sec |
| 8 | Check rewards (optional) | No | 10-20 sec |
| 9 | Final review | No | 5-10 sec |
| 10 | Pay | Yes | Varies by method |

**Total Minimum Time**: ~10-15 seconds (if no modifications)  
**Total Average Time**: ~2-3 minutes (with optional reviews)  
**Total Maximum Time**: ~5-10 minutes (with all options explored)

## Session Expiration & Re-authentication

### Session Timeout
- **Duration**: Typically 24-48 hours of inactivity
- **Warning**: System may warn user before expiration
- **Expired Session**: User prompted to re-login via WhatsApp OTP

### Auto Re-login
- If session expired, user clicks FLIK button again
- System detects expired session
- Presents WhatsApp login (not guest option)
- Same WhatsApp number auto-fills for convenience

## Best Practices for Registered Users

1. ✅ **Keep Address Updated**: Review saved addresses are current
2. ✅ **Save Multiple Addresses**: Add office, home, family locations
3. ✅ **Use Available Discounts**: Always check discount section before paying
4. ✅ **Monitor Rewards**: Check reward balance regularly
5. ✅ **Logout on Shared Devices**: Don't leave session active on public computers

## Security for Registered Users

- ✅ Session tokens secured with expiration
- ✅ Payment methods stored securely (tokenized, not raw card data)
- ✅ Two-factor verification via WhatsApp OTP
- ✅ Account activity logged for fraud detection
- ✅ GDPR compliant data storage and handling

## Related Documentation

- [Guest Checkout Flow](./guest-checkout.md) - Compare with guest experience
- [Login & OTP Flow](./login-checkout.md) - How users register/login
- [Address Management Feature](../features/address-management.md)
- [Courier Selection Feature](../features/courier-selection.md)
- [Payment Methods Feature](../features/payment-methods.md)
- [Discounts & Vouchers Feature](../features/discounts-vouchers.md)
- [Rewards System Feature](../features/rewards.md)

---

**Last Updated**: April 24, 2026  
**Version**: 1.0.0

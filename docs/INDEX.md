# FLIK Checkout Documentation Index

Complete navigation and index for all FLIK Checkout documentation.

## Getting Started

- [Main README](../README.md) - Overview and quick links
- [Integration Setup](./integration/setup.md) - How to add FLIK Checkout to your website

## User Flows (Step-by-Step Guides)

### 1. Guest Checkout
**File**: [`flows/guest-checkout.md`](./flows/guest-checkout.md)
**Who**: New users, non-registered customers
**Duration**: 10 steps, ~2-3 minutes total
**Key Steps**:
- Entry point and button click
- Choose guest checkout
- Enter name and email
- Add delivery address with map
- Courier auto-selection and options
- Payment method selection
- Discount application
- Final payment

### 2. Login & OTP
**File**: [`flows/login-checkout.md`](./flows/login-checkout.md)
**Who**: Registered users, returning customers
**Authentication**: WhatsApp OTP verification
**Key Steps**:
- WhatsApp login page
- OTP entry and verification
- Auto-filled checkout (for existing users)
- New user account creation flow

### 3. Registered User Checkout
**File**: [`flows/registered-user-checkout.md`](./flows/registered-user-checkout.md)
**Who**: Logged-in users with saved data
**Duration**: ~10-15 seconds minimum, ~2-3 minutes with options
**Key Steps**:
- Automatic session detection
- Auto-filled information display
- Optional modifications (address, courier, payment)
- View rewards and discounts
- Final payment

## Feature Documentation

### Address Management
**File**: [`features/address-management.md`](./features/address-management.md)
**Covers**:
- Address entry with map
- Saved address selection
- Recipient details
- Red zone detection
- Address validation
- Location-based courier routing

### Courier Selection  
**File**: [`features/courier-selection.md`](./features/courier-selection.md)
**Covers**:
- Auto-selection logic (cheapest option)
- Courier list and pricing
- Delivery time options
- Courier alternatives
- Red zone surcharges
- Courier availability by location

### Payment Methods
**File**: [`features/payment-methods.md`](./features/payment-methods.md)
**Covers**:
- E-wallets (OVO, ShopeePay, Dana, GoPay)
- QRIS payment
- Bank virtual accounts (BCA, MANDIRI, BNI, BRI, PERMATA, BSI)
- Payment gateway flows
- Refund processing
- Security measures

### Discounts & Vouchers
**File**: [`features/discounts-vouchers.md`](./features/discounts-vouchers.md)
**Covers**:
- FLIK system vouchers
- Merchant-specific vouchers
- Voucher application methods
- Discount restrictions and eligibility
- Guest vs. registered user discounts
- Error handling

### Rewards System
**File**: [`features/rewards.md`](./features/rewards.md)
**Covers**:
- Merchant rewards
- FLIK platform rewards
- Earning rewards on purchase
- Applying earned rewards
- Reward balances and expiration
- VIP tier programs

### Store Pickup
**File**: [`features/store-pickup.md`](./features/store-pickup.md)
**Covers**:
- Enabling pickup feature
- Tabbed interface (ship vs. pickup)
- Store location selection
- Operating hours
- Pickup process
- Benefits vs. limitations

### Merchant Configuration
**File**: [`features/merchant-configurations.md`](./features/merchant-configurations.md)
**Covers**:
- Enabling/disabling features
- Payment method configuration
- Discount management
- Reward program setup
- Store pickup locations
- Transaction limits

## How to Use This Documentation

### For Users
1. Start with [Main README](../README.md)
2. Choose your scenario:
   - **New customer?** → Read [Guest Checkout Flow](./flows/guest-checkout.md)
   - **Returning customer?** → Read [Registered User Checkout](./flows/registered-user-checkout.md)
   - **Need login help?** → Read [Login & OTP Flow](./flows/login-checkout.md)
3. Reference specific features as needed

### For Merchants
1. Review [Merchant Configuration](./features/merchant-configurations.md)
2. Set up features you want to enable
3. Refer to individual feature docs for detailed setup
4. Use [Integration Guide](./integration/setup.md) to add to website

### For Developers
1. Start with [Integration Setup](./integration/setup.md)
2. Follow embed code or API integration path
3. Reference API examples in feature docs
4. Implement webhook handlers
5. Test all payment methods and edge cases

### For Support/QA
1. Reference specific flow documentation for user journey
2. Check feature docs for functionality details
3. Use troubleshooting sections in each doc
4. Reference screenshots for visual verification

## Quick Reference by User Type

### Guest User Path
```
Entry Point → Guest Checkout → Name/Email → 
Address → Courier → Payment → Success
```
**Time**: 2-3 minutes
**Documents**: [Guest Checkout](./flows/guest-checkout.md)

### Registered User Path
```
Entry Point → WhatsApp Login → OTP →
Auto-filled Checkout → (Optional modifications) → Payment → Success
```
**Time**: 10-15 seconds (minimum) to 2-3 minutes
**Documents**: [Login](./flows/login-checkout.md), [Registered](./flows/registered-user-checkout.md)

### Pickup Customer Path
```
Entry Point → Choose "Ambil di Toko" → Select Store →
Payment → Pickup at Store
```
**Time**: 1-2 minutes
**Documents**: [Store Pickup](./features/store-pickup.md)

## Features by Availability

### Available to All Users
- ✅ Address Entry (new address)
- ✅ Courier Selection
- ✅ All Payment Methods
- ✅ FLIK System Vouchers (mostly)
- ✅ Store Pickup (if merchant enabled)

### Registered Users Only
- ✅ Saved Address Selection
- ✅ Multiple Saved Addresses
- ✅ Rewards Programs
- ✅ Full Discount Selection
- ✅ Some Merchant Vouchers

### Merchant-Dependent
- 🔀 Store Pickup (if enabled by merchant)
- 🔀 Specific Payment Methods
- 🔀 Merchant Vouchers
- 🔀 Reward Programs
- 🔀 Operating Hours

## Search by Scenario

### "I want to..."

**...complete my purchase quickly**
- Read: [Registered User Checkout](./flows/registered-user-checkout.md)
- Time: 10-15 seconds

**...save my address for next time**
- Read: [Address Management](./features/address-management.md)
- Action: Create account/register

**...find a discount**
- Read: [Discounts & Vouchers](./features/discounts-vouchers.md)
- Time: ~1 minute

**...earn rewards**
- Read: [Rewards System](./features/rewards.md)
- Action: Make purchase as registered user

**...pick up in-store**
- Read: [Store Pickup](./features/store-pickup.md)
- Check: Merchant must have pickup enabled

**...integrate FLIK Checkout**
- Read: [Integration Setup](./integration/setup.md)
- Time: ~5-10 minutes

**...understand red zones**
- Read: [Address Management](./features/address-management.md) (Red Zone section)
- Impact: Higher costs, longer delivery times

**...troubleshoot payment issues**
- Read: [Payment Methods](./features/payment-methods.md) (Common Issues section)
- Also check: Specific feature troubleshooting

## File Structure

```
docs/
├── INDEX.md (this file)
├── flows/
│   ├── guest-checkout.md
│   ├── login-checkout.md
│   └── registered-user-checkout.md
├── features/
│   ├── address-management.md
│   ├── courier-selection.md
│   ├── payment-methods.md
│   ├── discounts-vouchers.md
│   ├── rewards.md
│   ├── store-pickup.md
│   └── merchant-configurations.md
└── integration/
    └── setup.md

assets/
└── screenshots/
    ├── entry-point/
    ├── guest-checkout/
    ├── login-flow/
    ├── registered-checkout/
    └── features/
```

## Version Information

- **Documentation Version**: 1.0.0
- **Last Updated**: April 24, 2026
- **Coverage**: All features including guest, login, and registered user flows
- **Platforms**: Desktop and Mobile Web (responsive)

## Support & Updates

For updates, corrections, or suggestions:
- Email: support@flik.co.id
- GitHub Issues: https://github.com/raam-flik/FLIK-Checkout-Documentation/issues
- Community: https://community.flik.co.id

---

**Last Updated**: April 24, 2026

# FLIK Checkout Documentation

Welcome to the FLIK Checkout official documentation. This comprehensive guide covers all features, user flows, and integrations for the FLIK 1-Click Checkout solution.

## Overview

**FLIK Checkout** is a one-click checkout solution designed to simplify the payment experience for customers. Similar to Shopify's Shop app or Bolt.com, FLIK Checkout allows registered users to complete purchases with minimal steps by pre-filling their address, contact information, and payment method.

### Key Features

- **One-Click Checkout**: Registered users can complete purchases instantly with saved data
- **Guest Checkout**: Frictionless checkout for new customers without account creation
- **WhatsApp Authentication**: Login via WhatsApp OTP for seamless verification
- **Smart Courier Selection**: Automatic selection of the most cost-effective shipping option
- **Multiple Payment Methods**: Support for wallets, virtual accounts, QRIS, and more
- **Merchant Flexibility**: Optional offline store pickup feature
- **Address Management**: Full address book with map integration
- **Discount & Rewards**: Voucher support and reward programs for registered users

## Documentation Structure

### Quick Links

- **[Getting Started](#getting-started)** - Entry point and initial setup
- **[User Flows](./docs/flows/)** - Complete checkout journey documentation
- **[Features](./docs/features/)** - Detailed feature explanations
- **[Integration Guide](./docs/integration/)** - Developer integration instructions

### Flows

1. **[Guest Checkout Flow](./docs/flows/guest-checkout.md)** - Complete journey for new/non-registered users
2. **[Login & OTP Flow](./docs/flows/login-checkout.md)** - WhatsApp authentication process
3. **[Registered User Flow](./docs/flows/registered-user-checkout.md)** - Experience for logged-in users with saved data

### Features

1. **[Address Management](./docs/features/address-management.md)** - Address selection and management with map integration
2. **[Courier Selection](./docs/features/courier-selection.md)** - Shipping method and courier selection
3. **[Payment Methods](./docs/features/payment-methods.md)** - All supported payment options
4. **[Discounts & Vouchers](./docs/features/discounts-vouchers.md)** - Voucher application and restrictions
5. **[Rewards System](./docs/features/rewards.md)** - Merchant rewards and loyalty programs
6. **[Store Pickup](./docs/features/store-pickup.md)** - Optional offline store pickup feature
7. **[Merchant Configuration](./docs/features/merchant-configurations.md)** - Merchant-level settings and toggles

### Integration

1. **[Setup Guide](./docs/integration/setup.md)** - How to integrate FLIK Checkout on your website
2. **[API Reference](./docs/integration/api-reference.md)** - API endpoints and webhooks

## Getting Started

### For Merchants

To enable FLIK Checkout on your website:

1. Register your merchant account with FLIK
2. Generate your FLIK button/widget code
3. Add the code to your checkout page
4. Configure your merchant settings (e.g., enable/disable store pickup)
5. Test with guest and registered user flows

### For Users

**First Time (Guest Checkout)**:
1. Click "FLIK Buy it Now" button on merchant website
2. Enter your name and email
3. Fill in shipping address
4. Select courier and payment method
5. Complete payment

**Registered Users**:
1. Click "FLIK Buy it Now" button
2. Login via WhatsApp OTP
3. Confirm pre-filled information
4. Complete payment

### For Developers

Refer to the [Integration Guide](./docs/integration/setup.md) for:
- Button integration code
- Webhook callbacks
- Error handling
- Testing procedures

## User Personas

### Guest User (Non-Registered)
- New to FLIK checkout
- No account created
- Must fill all information
- Limited discount availability
- One-time experience unless they register later

### Registered User
- Has existing FLIK account
- Logged in via WhatsApp OTP
- Auto-filled address and payment method
- Access to saved addresses and payment methods
- Eligible for rewards and personalized discounts

### Merchant
- Store owner using FLIK Checkout
- Can customize checkout experience
- Can enable/disable features (e.g., store pickup)
- Can view transaction analytics
- Can manage customer rewards

## Key User Journey Stages

### 1. Entry Point
User visits merchant's website and sees FLIK Checkout button with promotional banner.

### 2. Session Check
System determines if user is registered with active session:
- **Yes**: Skip to registered user checkout
- **No**: Show login or guest checkout options

### 3. Authentication
User either logs in via WhatsApp or continues as guest.

### 4. Address Selection
User selects or adds delivery address (system validates against red zones).

### 5. Courier Selection
System suggests cheapest option; user can select alternatives.

### 6. Payment Method
User selects from available payment methods (determined by merchant config).

### 7. Confirmation & Payment
User reviews order and completes payment.

## Merchant Variations

This documentation covers two primary merchant configurations:

### Standard Merchant (No Pickup Feature)
- Only shipping options available
- Address field is required
- Example: ZMNow

### Merchant with Store Pickup
- Tabbed interface for shipping vs. pickup
- Users can choose delivery method
- "Lokasi Toko" (Store Location) field replaces address when pickup selected
- Example: Human Greatness

## Platform Coverage

- ✅ Desktop (Full featured)
- ✅ Mobile Web (Full featured, responsive)
- Note: All documentation includes both Desktop and Mobile Web screenshots

## Important Concepts

### Red Zone
Areas with limited or restricted delivery coverage. Characterized by:
- Extended delivery timelines (5-10+ days vs. standard 1-3 days)
- Additional surcharges (20-50%+ extra cost)
- Limited carrier options
- Special handling requirements

### Courier Auto-Selection
When user selects an address, the system automatically chooses the most cost-effective courier (cheapest "Ongkos Kirim").

### Payment Method Support
- E-wallets (OVO, Dana, GoPay, etc.)
- Virtual Accounts (BCA VA, MANDIRI VA, BNI VA, BRI VA, PERMATA VA, BSI VA)
- QRIS (Default for registered users)
- Bank Transfer
- Cash on Delivery (if enabled by merchant)

### Discount Types
- **FLIK Vouchers**: Available to all users
- **Guest Vouchers**: Limited selection for guest users
- **Merchant Vouchers**: Specific to merchant (guest users may not be eligible)

## Version Information

- **Current Version**: 1.0.0
- **Last Updated**: April 24, 2026
- **Status**: Active & Maintained

## Need Help?

- Review the specific flow documentation for step-by-step guidance
- Check feature documentation for detailed feature explanations
- Refer to integration guide for developer implementation
- Contact support@flik.co.id for additional assistance

---

**For Internal Teams & Developers**  
This documentation is designed to be comprehensive and accessible for both product teams and development teams. Use the navigation above to find the specific information you need.

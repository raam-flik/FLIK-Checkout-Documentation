# Payment Methods Feature

Complete guide to all supported payment methods in FLIK Checkout.

## Overview

FLIK Checkout supports multiple payment methods organized in categories:

- **E-Wallets**: OVO, ShopeePay, Dana, GoPay
- **QRIS**: QR code-based instant payment
- **Virtual Accounts**: Bank virtual accounts for transfers
- **Bank Transfer**: Direct bank transfers
- **Other**: Cash on Delivery (if enabled by merchant)

## Payment Methods Selection

### Payment Modal

**Desktop View**:
![Desktop Payment Methods](../../assets/screenshots/features/Desktop%20-%2010.png)

**Mobile Web View**:
![Mobile Payment Methods](../../assets/screenshots/features/MWeb%20-%2010.png)

### Modal Structure

#### E-Wallet Category:
- **OVO** - "Pay using OVO" with "Lanjutkan" button
- **ShopeePay** - "Pay using ShopeePay" with "Lanjutkan" button
- **Dana** - "Pay using Dana" with "Lanjutkan" button
- **GoPay** - "Pay using GoPay" with "Lanjutkan" button

Each wallet shows brand icon and option to proceed to that payment gateway.

#### QRIS Category:
- **QRIS** - "Pay using QR code"
- Radio button for selection
- Instructions provided on payment gateway

#### Virtual Account Category:
- **BCA VA** - Bank Central Asia Virtual Account
- **MANDIRI VA** - Bank MANDIRI Virtual Account
- **BNI VA** - Bank BNI Virtual Account
- **BRI VA** - Bank BRI Virtual Account
- **PERMATA VA** - Bank PERMATA Virtual Account
- **BSI VA** - Bank BSI Virtual Account

Each VA shows bank icon and option to select.

### Selection Process

1. **View Methods**: All available payment methods displayed
2. **Select**: Click "Lanjutkan" (wallet) or radio button (other methods)
3. **Confirm**: Selection saved to checkout session
4. **Return**: Back to checkout page showing selected payment method

## Payment Methods by Category

### E-Wallets (Instant, Most User-Friendly)

**OVO**:
- Indonesian digital wallet
- Instant payment and confirmation
- Requires OVO app or account
- Refunds instantly to OVO balance
- User must click "Lanjutkan" and complete OVO authorization

**ShopeePay**:
- E-commerce integrated wallet
- Works with Shopee ecosystem
- Instant payment
- Cashback often available
- Refunds to ShopeePay balance

**Dana**:
- Indonesian fintech wallet
- Instant payment processing
- No app required (web-based)
- Good for first-time users
- Growing adoption

**GoPay**:
- Gojek ecosystem wallet
- Integrated with transport/food delivery
- Instant payment
- Common in Indonesia
- User must have GoPay account/balance

### QRIS (Scan-to-Pay)

**What is QRIS?**:
- Quick Response Code Indonesian Standard
- National payment standard in Indonesia
- Works with any bank or e-wallet that supports QRIS
- User scans QR code with banking app or wallet

**QRIS Advantages**:
- ✅ Works with multiple payment sources
- ✅ User can pay with any bank
- ✅ Standardized and secure
- ✅ Popular and reliable
- ✅ Default for registered users

**QRIS Payment Flow**:
1. User selects QRIS at checkout
2. Payment page shows QR code
3. User opens their banking app or e-wallet
4. User scans QRIS code
5. Amount and merchant info shown in app
6. User confirms and pays
7. Instant confirmation and redirect

### Virtual Accounts (Bank Transfer)

**How VA Works**:
1. System generates unique virtual account number
2. User transfers exact amount to VA number
3. FLIK system detects transfer
4. Order confirmed automatically
5. Refunds returned to same account

**Bank Virtual Accounts Supported**:

| Bank | Account Format | Transfer Fee |
|------|---|---|
| **BCA VA** | 10-digit unique number | Standard BCA transfer fee |
| **MANDIRI VA** | 10-digit unique number | Standard MANDIRI transfer fee |
| **BNI VA** | 10-digit unique number | Standard BNI transfer fee |
| **BRI VA** | 10-digit unique number | Standard BRI transfer fee |
| **PERMATA VA** | 10-digit unique number | Standard PERMATA transfer fee |
| **BSI VA** | 10-digit unique number | Standard BSI transfer fee |

**VA Advantages**:
- ✅ No app required (use online banking)
- ✅ Works with all bank accounts
- ✅ Secure (bank-to-bank transfer)
- ✅ Transaction recorded in bank statement
- ⚠️ May take 1-2 hours to confirm (vs instant wallets)

**VA Limitations**:
- ⚠️ Must transfer exact amount
- ⚠️ Transfer from different account may cause issues
- ⚠️ Confirmation takes longer (1-2 hours vs instant)
- ⚠️ Transfer fee applies from user's bank

## Default Payment Methods

### For Registered Users:
- **Default**: QRIS
- **Reason**: Highest transaction volume, user familiarity
- **Can Change**: Select any other method anytime

### For Guest Users:
- **Default**: First method in list (usually first E-wallet)
- **Reason**: Quick and easy for first-time users
- **Can Change**: Select any other method anytime

### How to Change Default:
1. Click "Metode Pembayaran" section on checkout
2. Payment modal opens
3. Select different payment method
4. Confirm selection (auto-returns to checkout)

## Payment Gateway Redirect

After selecting payment method and clicking "Bayar Sekarang" (Pay Now):

1. **System Processes**: Validates checkout data
2. **Creates Transaction**: Transaction ID generated
3. **Redirects User**: To payment gateway specific to selected method
4. **Payment Gateway**: Shows instructions for selected method
5. **User Pays**: Completes payment via chosen method
6. **Confirmation**: Returns to merchant with order confirmation

## Payment Gateway Pages

### QRIS Payment Page:
Shows:
- Transaction ID
- Total amount due
- QR code for scanning
- Payment deadline
- Instructions for each payment method
- Option to download QR code

### Bank VA Payment Page:
Shows:
- Virtual account number
- Account holder name
- Exact amount to transfer
- Bank transfer instructions
- Payment deadline

### E-Wallet Payment Page:
Redirects to wallet provider:
- OVO redirects to OVO app/website
- ShopeePay redirects to ShopeePay app/website
- Dana redirects to Dana app/website
- GoPay redirects to GoPay/Gojek app

## Post-Payment Handling

### Successful Payment:
- ✅ Merchant receives order
- ✅ User receives confirmation email
- ✅ Tracking number provided
- ✅ Order shows in user's history (if registered)

### Failed Payment:
- ❌ Payment not processed
- ⚠️ Error message shown
- ✅ User can try again with same or different method
- ✅ No charge applied for failed attempts

### Pending Payment:
- ⏳ For VA transfers: Waiting for bank confirmation
- Status: "Pending" shown in order
- Confirmation within 1-2 hours
- Email notification sent when confirmed

## Payment Security

### Encryption:
- ✅ SSL/TLS encryption for all payment data
- ✅ PCI DSS compliant
- ✅ No raw card data stored
- ✅ Secure payment tokenization

### Fraud Prevention:
- ✅ Real-time fraud detection
- ✅ Transaction limits enforced
- ✅ Unusual activity monitoring
- ✅ Multi-verification for large transactions

### User Verification:
- ✅ Email verification required
- ✅ Phone verification via OTP (login users)
- ✅ Transaction confirmation required
- ✅ Refund processed to original payment source

## Refund Policy

### Refund Eligibility:
- ✅ Full refund if order cancelled before shipment
- ✅ Partial refund for returned items
- ⚠️ Refund only if merchant refund policy allows
- ❌ Refund cannot be paid to different payment method

### Refund Processing:
- **E-Wallet**: Refund within 30 minutes - 2 hours
- **QRIS**: Refund within 1-2 hours
- **Bank VA**: Refund within 1-2 business days

### Refund Status:
- User notified via email when refund processed
- Refund shown in wallet/bank account history
- Refund ID provided for tracking

## Payment Methods Comparison

| Method | Speed | Convenience | Fees | Best For |
|--------|-------|-------------|------|----------|
| OVO | Instant | Very High | None | Quick payment |
| ShopeePay | Instant | Very High | None | Shopee users |
| Dana | Instant | High | None | Fintech users |
| GoPay | Instant | Very High | None | Gojek users |
| QRIS | Instant | Medium | Varies | Registered users |
| BCA VA | 1-2 hrs | Medium | Low | Savings accounts |
| MANDIRI VA | 1-2 hrs | Medium | Low | MANDIRI customers |
| BNI VA | 1-2 hrs | Medium | Low | BNI customers |
| BRI VA | 1-2 hrs | Medium | Low | BRI customers |
| PERMATA VA | 1-2 hrs | Medium | Low | PERMATA customers |
| BSI VA | 1-2 hrs | Medium | Low | Islamic banking |

## Payment Method Availability

### By Merchant:
- Merchant can enable/disable specific payment methods
- Different merchants may offer different options
- Payment methods configuration in merchant settings
- FLIK determines defaults based on transaction volume

### By Region:
- All methods available nationwide
- No regional restrictions
- International payment methods not yet supported
- Plans for international payment expansion

### By User Type:
- **Guest Users**: All available methods can be used
- **Registered Users**: All available methods + saved methods
- **High-Risk Users**: May have limited options pending verification

## Common Payment Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| Payment declined | Insufficient balance | Check wallet/account balance before paying |
| OVO not connecting | OVO app not logged in | Login to OVO app or authorize on web |
| VA number incorrect | User copied wrong | Copy from payment page again (don't type) |
| Payment not confirmed | Bank processing delay | Wait 1-2 hours, refresh order page |
| Duplicate charge | Double-clicked payment button | Contact support if charged twice |
| Wrong amount charged | Merchant error or scam | Contact merchant or support immediately |

## Developer Integration

### Select Payment Method API:
```
POST /checkout/payment-method
{
  "checkoutSessionId": "session_123",
  "paymentMethod": "qris"
}
```

### Validate Payment Method:
```
GET /checkout/payment-methods/{method}
```

Returns: Available, fees, processing time

## Best Practices

### For Users:
1. ✅ **Use E-Wallet**: Fastest and easiest for instant payment
2. ✅ **Check Balance**: Ensure sufficient balance before selecting
3. ✅ **Save Methods**: Register users can save preferred method
4. ✅ **Keep Updated**: Update payment method info if changed
5. ✅ **Secure Account**: Use strong passwords for wallets

### For Merchants:
1. ✅ **Offer Multiple Options**: Increase payment success rate
2. ✅ **Prominent Display**: Show all available methods clearly
3. ✅ **Test Methods**: Test each method regularly
4. ✅ **Monitor Failures**: Track which methods have issues
5. ✅ **Update Regularly**: Add new payment methods as available

## Related Documentation

- [Registered User Checkout](../flows/registered-user-checkout.md)
- [Guest Checkout](../flows/guest-checkout.md)
- [Payment Security Standards](../integration/setup.md)

---

**Last Updated**: April 24, 2026  
**Version**: 1.0.0

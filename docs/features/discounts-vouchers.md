# Discounts & Vouchers Feature

Complete guide to applying discounts and vouchers in FLIK Checkout.

## Overview

FLIK Checkout supports multiple discount types:
- **FLIK System Vouchers**: Available to all users
- **Merchant Vouchers**: Specific to individual merchants (may be restricted to registered users)
- **Promotional Codes**: Time-limited promotions
- **Loyalty Rewards**: For registered users only
- **Cashback Programs**: Return customer rewards

## Discount Types

### FLIK System Vouchers
- Issued by FLIK platform
- Available to all users (guest and registered)
- Examples: "FLIK5", "FLIK15", "WEBSALE30"
- May have minimum purchase requirements
- Multiple vouchers often available simultaneously

### Merchant Vouchers
- Issued by individual merchants
- May be restricted to registered customers only
- Guest users may see "Grayed out" or "Not eligible" status
- Offer merchant-specific discounts
- Example: "ZMNOW SHIPPING" (merchant-specific promotion)

### Loyalty Rewards
- For registered users only
- Earned from previous purchases
- Automatically applied if available
- Don't require voucher code

## Discount Modal

### Guest User Discounts

**Desktop View**:
![Desktop Guest Discounts](../../assets/screenshots/features/Desktop%20-%2011b.png)

**Mobile View**:
![Mobile Guest Discounts](../../assets/screenshots/features/MWeb%20-%2011b.png)

### Registered User Discounts

**Desktop View**:
![Desktop Registered Discounts](../../assets/screenshots/features/Desktop%20-%2011a.png)

**Mobile View**:
![Mobile Registered Discounts](../../assets/screenshots/features/MWeb%20-%2011a.png)

### Modal Sections

#### Voucher Code Input:
- Text field: "Masukkan kode voucher disini" (Enter voucher code here)
- "Terapkan" (Apply) button

#### Promotions Already Applied:
- Shows currently active promotions
- Checkmark icon indicates "Active"
- Example: "ZMNOW SHIPPING Rp10,000" with checkmark

#### Reward Programs Section:
Shows available rewards (registered users only):
- **Merchant Rewards**: Balance and applicability
  - Example: "ZMNow Saldo: Rp0" - Merchant-specific balance
- **FLIK Rewards**: FLIK loyalty points
  - Example: "FLIK Reward Saldo: Rp0" - Platform loyalty
- Applicability notes show if reward can be used

#### FLIK Vouchers Section:
Available FLIK system vouchers with:
- Voucher code
- Discount amount or percentage
- Expiration status
- Minimum purchase requirement (if any)
- Plus icon (+) to add/apply voucher

**Examples**:
- "FLIK5 - Discount 5K"
- "BTWHG - Discount 20%"
- "WEBSALE30AGS_OVERLIMIT - Discount 30K (Min. pembelian Rp1,000)"

#### Merchant Vouchers Section:
Merchant-specific discounts:
- May show "GRATIS" (free) promotional codes
- May be restricted to registered users
- Plus icon (+) to apply
- Locked icon or grayed out if not eligible

**Example**: "NEW2M - Rp10,000.00 off entire order - For Customers who haven't purchased"

## Applying Discounts

### Method 1: Enter Voucher Code

1. Click "Masukkan kode voucher disini" field
2. Type voucher code (e.g., "FLIK5")
3. Click "Terapkan" (Apply) button
4. System validates:
   - Code exists
   - Code not expired
   - Minimum purchase met
   - User eligible for code
5. If valid: Discount applied, amount shown
6. If invalid: Error message shown, user can retry

### Method 2: Click Plus Icon

1. Find voucher in available list
2. Click "+" button next to voucher
3. Discount automatically applied
4. Amount deducted from order total
5. Voucher code shown as "Applied"

### Method 3: Auto-Apply Loyalty Rewards

For registered users:
1. System checks available reward balance
2. If balance > Rp0, offers to apply automatically
3. User can accept or skip
4. Applied rewards shown with checkmark

## Discount Restrictions

### Usage Limits:
- **One-time use**: Voucher can only be used once (per user or globally)
- **Stackable**: Some vouchers combine, others don't
- **Per-customer limit**: Limit how many times single customer can use
- **Expiration date**: After date passes, voucher invalid

### Product Restrictions:
- **Category-specific**: May only work on certain product categories
- **Merchant-specific**: May only work on purchases from specific merchant
- **Price minimum**: Minimum purchase amount required
- **Quantity minimum**: Minimum items required

### User Restrictions:
- **First-time buyers only**: New customer promotions
- **Registered users only**: Loyalty programs not for guests
- **High-volume customers**: Discounts for regular buyers
- **VIP members**: Special tier discounts

## Discount Eligibility

### Guest Users:
✅ Can apply:
- FLIK system vouchers
- Public promotional codes
- Some general merchant promotions

❌ Cannot apply:
- Merchant-specific vouchers (often)
- Loyalty rewards (no account to track)
- First-purchase-only codes (once account created)

### Registered Users:
✅ Can apply:
- All FLIK system vouchers
- All merchant vouchers
- Loyalty rewards automatically
- Merchant-specific promotions
- Purchase history-based discounts

❌ Cannot apply:
- Expired vouchers
- Code used up (if limit reached)
- Codes not eligible for their user tier

## Discount Application Examples

### Example 1: FLIK System Voucher
```
Order Subtotal: Rp143,000
Shipping: Rp11,000
Subtotal: Rp154,000

Apply: "FLIK5" (Discount Rp5,000)
Discount: -Rp5,000

Total: Rp149,000
```

### Example 2: Percentage Discount
```
Order Subtotal: Rp199,000
Shipping: Rp9,000
Subtotal: Rp208,000

Apply: "BTWHG" (Discount 20%)
Discount: -Rp41,600 (20% of Rp208,000)

Total: Rp166,400
```

### Example 3: Free Shipping
```
Order Subtotal: Rp199,000
Shipping: Rp10,000
Subtotal: Rp209,000

Apply: "ZMNOW SHIPPING" (Free Shipping)
Discount: -Rp10,000

Total: Rp199,000
```

### Example 4: Multiple Discounts (if stackable)
```
Order Subtotal: Rp500,000
Shipping: Rp50,000
Subtotal: Rp550,000

Apply: "SALE50K" (Discount Rp50,000)
Subtotal: Rp500,000

Apply: "LOYALT10" (Discount Rp50,000)
Subtotal: Rp450,000

Total: Rp450,000 (if stackable)
```

## Discount Status & Display

### On Checkout Page:
- Light blue info box: "Ssst.. kamu bisa lebih hemat!" (Psst.. you can save more!)
- Shows applicable discounts at a glance
- Click to open detailed discount modal

### In Order Summary:
- Shows itemized breakdown
- Discount line item shows deduction
- Final total reflects discount

### On Payment Page:
- Discount amount shown in transaction details
- Final amount user must pay

### On Receipt:
- Discount code(s) listed
- Amount saved shown
- Confirmation of applied discounts

## Error Handling

### Invalid Voucher Code:
- Error message: "Kode voucher tidak valid" (Invalid voucher code)
- Suggestion to check spelling
- Option to try different code

### Expired Voucher:
- Error message: "Voucher telah kadaluarsa" (Voucher has expired)
- Shows expiration date if applicable
- Suggests alternative vouchers

### Minimum Purchase Not Met:
- Error message: "Minimum pembelian tidak terpenuhi" (Minimum purchase not met)
- Shows required minimum amount
- Suggests adding items to reach minimum

### Not Eligible (Registered-only, etc.):
- Error message: "Anda tidak eligible untuk voucher ini" (You're not eligible)
- Explains restriction (e.g., "Registered users only")
- Suggests registering account

### Usage Limit Exceeded:
- Error message: "Voucher telah mencapai limit penggunaan" (Voucher usage limit reached)
- Explains limit (once per user, X times total, etc.)
- Suggests alternative vouchers

## Merchant Perspective

### Voucher Management:
Merchants can:
- Create custom vouchers
- Set discount amount
- Set expiration dates
- Set minimum purchase
- Set usage limits
- View redemption analytics
- Pause/resume vouchers

### Best Practices:
- Create limited-time promotions for urgency
- Set minimum purchase to increase order value
- Use customer segments for targeted promotions
- Monitor redemption rates to adjust offers

## Developer Integration

### Apply Voucher API:
```
POST /checkout/apply-discount
{
  "checkoutSessionId": "session_123",
  "voucherCode": "FLIK5"
}
```

Returns:
```json
{
  "valid": true,
  "discountAmount": 5000,
  "totalAfterDiscount": 149000
}
```

### Get Available Vouchers:
```
GET /checkout/available-vouchers?userId={user_id}
```

Returns list of applicable vouchers with amounts

## Best Practices

### For Users:
1. ✅ Always check discount section
2. ✅ Apply highest-value discounts first
3. ✅ Check expiration dates before applying
4. ✅ Read restrictions carefully
5. ✅ Screenshot good deals for later

### For Merchants:
1. ✅ Offer regular promotions
2. ✅ Create urgency with expiration dates
3. ✅ Make discounts easy to find
4. ✅ Communicate restrictions clearly
5. ✅ Track discount ROI

## Related Documentation

- [Guest Checkout Flow](../flows/guest-checkout.md)
- [Registered User Checkout](../flows/registered-user-checkout.md)
- [Rewards System](./rewards.md)

---

**Last Updated**: April 24, 2026
**Version**: 1.0.0

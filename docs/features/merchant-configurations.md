# Merchant Configuration & Settings

Complete guide to FLIK Checkout configuration options for merchants.

## Overview

Merchants can customize their FLIK Checkout experience by:
- Enabling/disabling features
- Configuring payment methods
- Setting up pickup locations
- Managing discount programs
- Customizing checkout appearance
- Setting transaction limits

## Configuration Options

### 1. Store Pickup Feature

#### Enable Store Pickup:
- **Toggle**: On/Off
- **When On**: Customers see "Ambil di toko" (Pickup) tab
- **When Off**: Only delivery option shown (like ZMNow example)

#### Store Locations:
When pickup enabled, merchant must:
- Add store address(es)
- Set operating hours for each store
- Provide contact information
- Update hours as needed

#### Related Feature:
See [Store Pickup Documentation](./store-pickup.md)

### 2. Payment Methods

#### Available Payment Methods:
Merchant can enable/disable:
- **E-Wallets**: OVO, ShopeePay, Dana, GoPay
- **QRIS**: Instant payment via QR
- **Virtual Accounts**: Bank VA options
- **Bank Transfer**: Direct transfers
- **Cash on Delivery**: If permitted
- **Installment Plans**: If offered

#### Configuration:
- Select which methods to accept
- Disable problematic methods
- Set payment method order/priority
- Add payment instructions (if needed)

### 3. Discount Management

#### Merchant Vouchers:
- Create custom voucher campaigns
- Set discount amount/percentage
- Set usage limits
- Set expiration dates
- Configure target audience

#### Restricted/Unrestricted:
- Mark if guest-eligible
- Mark if registered-only
- Set minimum purchase requirements

#### Performance Tracking:
- View redemption rates
- Track discount ROI
- Monitor usage patterns
- Pause/resume campaigns

### 4. Reward Program Configuration

#### Program Details:
- **Earn Rate**: Percentage customers earn (e.g., 10% cashback)
- **Minimum Purchase**: Minimum order to earn rewards
- **Maximum Reward**: Cap on earnings per transaction
- **Expiration Period**: How long rewards valid

#### Program Eligibility:
- All customers or registered only
- First-purchase bonuses
- VIP tier multipliers
- Seasonal adjustments

#### Redemption Rules:
- Can be combined with vouchers
- Applicable to all products or specific categories
- Minimum balance to redeem
- Restrictions on redemption

### 5. Checkout Customization

#### Branding:
- Logo display
- Color scheme
- Custom messaging
- Promotional banners

#### Form Fields:
- Which fields are required
- Additional custom fields
- Field order/priority

#### Notifications:
- Email notification settings
- SMS notification settings
- Template customization
- Frequency settings

### 6. Transaction & Risk Settings

#### Limits:
- **Maximum Transaction Amount**: Cap per order
- **Minimum Transaction Amount**: Minimum order value
- **Daily Volume Limit**: Maximum daily transactions
- **Velocity Limits**: Prevent rapid transactions

#### Fraud Prevention:
- Address verification requirements
- Phone verification requirements
- Email confirmation requirements
- CVC verification

#### Refund Policy:
- Auto-refund timeframe
- Manual approval required (Y/N)
- Refund method restrictions
- Chargeback handling

## Configuration Examples

### Example 1: Human Greatness (With Pickup)

**Store Pickup**: ✅ ENABLED
- Primary Warehouse: Kota Bandung (08:00-17:00)
- Multiple locations available
- Customers see both shipping and pickup options

**Payment Methods**: ✅ All enabled
- OVO, ShopeePay, Dana, GoPay
- QRIS, Bank VAs
- Full payment flexibility

**Rewards Program**: ✅ ACTIVE
- 10% merchant reward rate
- All purchases eligible
- Can combine with FLIK rewards

**Vouchers**: ✅ Multiple campaigns
- "ZMNOW SHIPPING" (Free shipping)
- Limited-time promotions
- Some registered-user-only

### Example 2: ZMNow (No Pickup, Standard)

**Store Pickup**: ❌ DISABLED
- Only delivery option
- Customers must provide address
- No pickup tab shown

**Payment Methods**: ✅ All enabled
- Standard e-wallet support
- QRIS and VA options
- Full payment flexibility

**Rewards Program**: ✅ ACTIVE
- Loyalty program enabled
- Merchant rewards for repeat customers
- Incentives for higher spend

**Vouchers**: ✅ Active campaigns
- Regular promotional codes
- First-purchase discounts
- Seasonal promotions

## Managing Configurations

### Access Configuration Panel:
1. Login to merchant dashboard
2. Navigate to "Settings" or "Checkout Configuration"
3. Select feature to configure
4. Make changes
5. Save and apply

### Testing Configuration:
- Use test mode before going live
- Test each payment method
- Verify discount application
- Confirm email notifications
- Test pickup process (if enabled)

### Monitoring & Analytics:
- Track configuration effectiveness
- Monitor feature usage
- Analyze payment method preferences
- Review discount redemption
- Adjust based on data

## Best Practices for Merchants

### Payment Methods:
1. ✅ Enable multiple payment methods (increase conversion)
2. ✅ Monitor payment failures
3. ✅ Disable methods with high failure rates
4. ✅ Test all methods monthly
5. ✅ Update payment provider API keys

### Discounts:
1. ✅ Create regular promotions
2. ✅ Use time-limited discounts for urgency
3. ✅ Track discount ROI carefully
4. ✅ Balance discount depth vs. profitability
5. ✅ A/B test different discount offers

### Store Pickup (if enabled):
1. ✅ Keep store hours accurate
2. ✅ Update store addresses immediately if changed
3. ✅ Train staff on pickup procedures
4. ✅ Maintain store appearance for customer experience
5. ✅ Track pickup vs. delivery ratios

### Rewards Program:
1. ✅ Set earn rate that's sustainable
2. ✅ Promote program to customers
3. ✅ Make redemption easy
4. ✅ Monitor program profitability
5. ✅ Adjust rates based on usage

### General:
1. ✅ Regularly review all settings
2. ✅ Test configuration changes
3. ✅ Monitor customer feedback
4. ✅ Stay updated on new features
5. ✅ Contact support for optimization advice

## Common Configuration Issues

| Issue | Solution |
|-------|----------|
| Customers can't pay | Check payment methods enabled, verify API keys |
| Store locations not showing | Verify store locations added, check timezone |
| Discounts not applying | Check discount eligibility, verify expiration date |
| Rewards not crediting | Verify program enabled, check minimum requirements |
| Notifications not sent | Check email settings, verify recipient email |
| Configuration reverted | Check if auto-saved properly, try again |

## Security Considerations

### Configuration Security:
- ✅ Only merchant admins can modify settings
- ✅ Changes logged for audit trail
- ✅ Test mode to prevent accidental changes
- ✅ Configuration backups maintained
- ✅ API keys encrypted and not displayed

### Sensitive Configuration:
- ✅ Payment API keys secured
- ✅ Discount codes not shared publicly before launch
- ✅ Reward program details reviewed before promotion
- ✅ Customer data protection verified
- ✅ PCI DSS compliance maintained

## API Integration (Developers)

### Get Merchant Configuration:
```
GET /merchants/{merchantId}/checkout-config
```

### Update Configuration:
```
PATCH /merchants/{merchantId}/checkout-config
{
  "paymentMethods": ["ovo", "qris", "bca_va"],
  "storePickupEnabled": true,
  "rewardRate": 10,
  "maxTransactionAmount": 10000000
}
```

### Store Locations:
```
GET /merchants/{merchantId}/stores
POST /merchants/{merchantId}/stores
PATCH /merchants/{merchantId}/stores/{storeId}
DELETE /merchants/{merchantId}/stores/{storeId}
```

## Differences Between Merchants

### Pickup Configuration:
- **Merchant A (With Pickup)**: Shows both shipping and pickup options
- **Merchant B (Without Pickup)**: Only shipping shown

### Payment Methods:
- Different merchants may support different payment methods
- Regional availability variations
- Integration status varies
- Legacy system constraints

### Discount Programs:
- FLIK system discounts available to all
- Merchant-specific vouchers vary
- Reward rates differ by merchant
- Eligibility rules merchant-specific

### Operating Hours:
- Pickup available during store hours only
- Different stores may have different hours
- Holiday schedules affect availability
- Hours must be kept accurate

## Related Documentation

- [Store Pickup Feature](./store-pickup.md)
- [Payment Methods Feature](./payment-methods.md)
- [Discounts & Vouchers Feature](./discounts-vouchers.md)
- [Rewards System Feature](./rewards.md)

---

**Last Updated**: April 24, 2026
**Version**: 1.0.0

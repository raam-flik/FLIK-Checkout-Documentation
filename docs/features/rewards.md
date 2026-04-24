# Rewards System Feature

Complete guide to the FLIK Checkout rewards and loyalty program.

## Overview

The **Rewards System** allows registered users to:
- Earn rewards/cashback from purchases
- See potential rewards before purchasing
- Apply earned rewards to future purchases
- Track reward balance and history
- Benefit from merchant-specific rewards programs

**Note**: Guest users are NOT eligible for rewards.

## Reward Types

### Merchant Rewards
- Issued by individual merchants
- Specific to each merchant
- Example: "ZMNow Saldo: Rp0" (ZMNow merchant reward balance)
- Cashback percentage varies by merchant
- Can be applied to purchases from that merchant only

### FLIK Rewards
- Issued by FLIK platform
- Available across all partner merchants
- Example: "FLIK Reward Saldo: Rp0" (FLIK loyalty program)
- Applies universally to all FLIK transactions
- Earned from every purchase

## Rewards Info Popup

Registered users can view estimated rewards before purchasing.

**Desktop View**:
![Rewards Info Popup](../../assets/screenshots/features/Desktop%20-%207.png)

### Popup Structure

#### Title:
- **"Potensi Reward"** (Potential Reward)

#### Main Message:
- **"Belanja terus, tetap hemat!"** (Keep shopping, stay economical!)
- **"Nikmati reward merchant hingga Rp9.950"** (Enjoy merchant rewards up to Rp9,950)

#### Detailed Explanation:
- **"Cashback Rp9.950 Merchant Reward akan kamu terima setelah transaksi selesai"**
  (You'll receive Rp9,950 Merchant Reward cashback after transaction completes)

#### How to Earn:
Shows three-step process:
1. **"Beli produk dari merchant FLIK Partners"** (Buy products from FLIK Partner merchants)
2. **"Setelah transaksi selesai, kamu akan dapat Merchant Reward"** (After transaction completes, you'll get Merchant Reward)
3. **"Gunakan Merchant Reward untuk transaksi selanjutnya"** (Use Merchant Reward for next transactions)

#### Closing:
- **"Tutup"** (Close) button to dismiss

## Rewards Calculation

### How Rewards Are Calculated:

```
Purchase Amount: Rp100,000
Merchant Reward Rate: 10%
Merchant Reward Earned: Rp10,000

+ 

FLIK Reward Rate: 2%
FLIK Reward Earned: Rp2,000

=

Total Rewards Earned: Rp12,000
```

### Reward Rates:
- **Merchant Rewards**: 5-15% typically (varies per merchant)
- **FLIK Rewards**: 1-3% typically (standard across platform)
- **Promotional Multipliers**: Up to 2x-3x during campaigns
- **VIP Tiers**: Higher rates for high-spending customers

### When Rewards Credited:
- **After Transaction Completes**: Not instant, after order confirmed
- **Same Day Usually**: Within 24 hours typically
- **Notification Sent**: Email confirmation of rewards earned
- **Visible in Account**: Instant availability after crediting

## Using Rewards

### Check Reward Balance

In the discount section on checkout page:
- **Reward Programs**: Shows current balance
- **Merchant Rewards**: Balance for current merchant
- **FLIK Rewards**: Total platform rewards balance
- **Applicability**: Shows if reward can be used (green = eligible)

### Apply Rewards

#### Automatic Application:
For registered users, if reward balance > Rp0:
- System may auto-apply rewards
- User can accept or decline
- Confirmation shown in discount section

#### Manual Application:
1. Click "Diskon" (Discount) section
2. Scroll to "Reward" section
3. See available reward balance
4. Click to apply reward
5. Amount deducted from total

## Reward Restrictions

### Usage Limits:
- **Minimum Balance**: May require Rp100 or more to use
- **Expiration**: Rewards may expire after certain period (e.g., 180 days)
- **One per Transaction**: Only one reward type per transaction
- **Partial Use**: Can use full balance or partial amount

### Merchant Rewards Restrictions:
- Only for purchases from issuing merchant
- Cannot combine with other merchant rewards (on same purchase)
- Can combine with FLIK rewards

### FLIK Rewards Restrictions:
- Can be used on any FLIK partner merchant
- Can combine with merchant-specific rewards
- Subject to minimum balance requirements

### Ineligibility Cases:
- New accounts (may have waiting period)
- Suspended accounts (due to fraud/chargebacks)
- Using different payment method than registered
- Purchase from non-partner merchants

## Rewards Display

### On Checkout Page:
```
Reward Programs section shows:
- ZMNow Saldo: Rp0 (Applicable: Rp0)
- FLIK Reward Saldo: Rp0 (Applicable: Rp0)
```

Indicates whether reward can be applied to current purchase.

### In Discount Modal:
Shows complete reward program information with:
- Current balance
- Applicable amount (may differ from balance)
- Earn rate for current purchase
- Expiration date
- Option to apply

### On Receipt:
- Rewards earned from transaction
- Previous balance
- New balance after purchase
- Timestamp of crediting

### In Account History:
- Running transaction log with rewards
- Earned vs. spent rewards
- Expiration warnings
- Balance over time

## Reward Expiration

### Expiration Policy:
- **Standard**: 180 days from earning date
- **Promotional**: May vary by campaign
- **VIP Tiers**: May have longer expiration
- **Frozen Accounts**: No expiration during freeze

### Expiration Warning:
- Email notification 30 days before expiration
- In-app notification when logging in
- Discount section highlights expiring rewards
- Dashboard shows countdown

### Expired Rewards:
- Automatically removed from balance
- Cannot be recovered
- Email confirmation sent
- Encourages urgency to use rewards

## Reward Redemption Examples

### Example 1: Merchant Reward Only
```
Purchase Amount: Rp100,000
Merchant Reward Balance: Rp15,000
Apply Merchant Reward: -Rp15,000

Order Total: Rp85,000
(After reward applied)
```

### Example 2: FLIK Reward Only
```
Purchase Amount: Rp100,000
FLIK Reward Balance: Rp10,000
Apply FLIK Reward: -Rp10,000

Order Total: Rp90,000
```

### Example 3: Both Rewards (if allowed)
```
Purchase Amount: Rp100,000
Merchant Reward: Rp15,000
FLIK Reward: Rp10,000
Apply Both: -Rp25,000

Order Total: Rp75,000
```

### Example 4: Earn Rewards on Purchase
```
Purchase Amount: Rp100,000
Merchant Rate: 10% → Earn Rp10,000
FLIK Rate: 2% → Earn Rp2,000

Total Rewards Earned: Rp12,000
New Merchant Balance: Rp25,000 → Rp35,000
New FLIK Balance: Rp18,000 → Rp20,000
```

## Reward Tiers & VIP Programs

### Tier-Based Rewards:
- **Bronze**: Standard earn rate, lower usage limits
- **Silver**: 1.2x earn rate, higher usage limits
- **Gold**: 1.5x earn rate, extended expiration
- **Platinum**: 2x earn rate, no expiration, exclusive perks

### Progression:
Based on lifetime spending:
- Bronze: Rp0 - Rp500,000 lifetime
- Silver: Rp500,000 - Rp2,000,000 lifetime
- Gold: Rp2,000,000 - Rp5,000,000 lifetime
- Platinum: Rp5,000,000+ lifetime

### Tier Benefits:
- Higher earn rates
- Longer expiration periods
- Lower minimum to redeem
- Priority support
- Exclusive promotions

## API Integration (Developers)

### Get Reward Balance:
```
GET /user/rewards
```

Returns:
```json
{
  "merchantRewards": {
    "balance": 15000,
    "applicableAmount": 15000,
    "expirationDate": "2026-10-24"
  },
  "flikRewards": {
    "balance": 10000,
    "applicableAmount": 10000,
    "expirationDate": "2026-10-24"
  }
}
```

### Apply Reward to Order:
```
POST /checkout/apply-reward
{
  "checkoutSessionId": "session_123",
  "rewardType": "merchant", // or "flik"
  "amount": 15000
}
```

### Get Potential Rewards for Purchase:
```
POST /checkout/calculate-rewards
{
  "merchantId": "zmn_123",
  "purchaseAmount": 100000
}
```

## Merchant Perspective

### Creating Reward Programs:
Merchants can:
- Set earn rate (e.g., 10% cashback)
- Set minimum purchase to earn
- Set expiration policy
- Create promotional multipliers
- Monitor redemption analytics

### Best Practices:
- Set reasonable earn rates (5-15%)
- Allow rewards to encourage repeat purchases
- Create tier-based incentives
- Promote program to customers
- Track ROI of rewards program

## Best Practices

### For Users:
1. ✅ Check reward balance regularly
2. ✅ Use rewards before expiration
3. ✅ Combine merchant + FLIK rewards when possible
4. ✅ Track reward earning on each purchase
5. ✅ Plan purchases to meet VIP tiers

### For Developers:
1. ✅ Validate reward eligibility before applying
2. ✅ Handle expiration gracefully
3. ✅ Show reward potential prominently
4. ✅ Send expiration notifications
5. ✅ Test reward redemption thoroughly

## Common Rewards Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| Reward not applied | Insufficient balance | Check balance, use available amount |
| Reward not earned | Account ineligible | Check account status, contact support |
| Reward expired | Unused past expiration | New rewards earned on future purchases |
| Partial redemption | Large balance, small purchase | Use full balance or manual amount |
| Cannot combine rewards | Policy restriction | Check if combination allowed |

## Related Documentation

- [Discounts & Vouchers](./discounts-vouchers.md)
- [Registered User Checkout](../flows/registered-user-checkout.md)

---

**Last Updated**: April 24, 2026
**Version**: 1.0.0

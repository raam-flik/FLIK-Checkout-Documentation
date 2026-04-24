# Courier Selection Feature

Complete guide to selecting shipping courier and delivery methods in FLIK Checkout.

## Overview

The **Courier Selection** feature allows users to:
- **View Available Couriers**: See all couriers that serve the delivery address
- **Compare Options**: See price and delivery time for each
- **Select Preferred Courier**: Choose based on speed, cost, or preference
- **Auto-Selection**: System defaults to cheapest option
- **Change Anytime**: Modify courier selection until payment

## Courier Auto-Selection

### Default Behavior

When user selects/changes their delivery address:
1. System validates address
2. System queries which couriers serve that area
3. **System automatically selects the cheapest courier**
4. Selection shown on checkout page (cannot proceed without courier)
5. User can see and select alternatives

### Auto-Selection Logic

```
For selected address:
├─ Get all available couriers
├─ Calculate lowest cost
└─ Select that courier as default
```

**Example**:
- Gojek Same Day: Rp26,500
- Gojek Instant: Rp50,000
- Grab Instant: Rp52,000
- **Grab Same Day: Rp17,000** ← Auto-selected (cheapest)
- J&T EZ: GRATIS (Free but 3-4 days)
- SiCepat Regular: GRATIS (Free but 2-3 days) ← Actually cheapest if free tier considered

**Note**: Free shipping options may not be auto-selected if delivery time is very long. System balances cost and reasonable delivery time.

## Courier Selection Modal

### Opening the Modal

User clicks on the "Pilih Kurir" (Select Courier) section on checkout page.

**Desktop View**:
![Desktop Courier Selection](../../assets/screenshots/features/Desktop%20-%2011.png)

**Mobile Web View**:
![Mobile Courier Selection](../../assets/screenshots/features/MWeb%20-%2011.png)

### Modal Structure

#### Title:
- **"Pilih Kurir"** (Select Courier)
- Simple, clear heading

#### Courier List

Each courier option shows:
1. **Courier Logo/Icon**: Visual identification
2. **Courier Name + Service Type**: e.g., "Gojek - Same Day"
3. **Pricing Information**:
   - Original price (struck through if on sale)
   - Discounted price shown in bold
   - Format: "( Rp36,500 Rp26,500 )" = "Old Price New Price"
4. **Delivery Time**: e.g., "Pengiriman ( 6 - 8 ) jam" (Delivery 6-8 hours)
5. **Radio Button**: For selection

#### Example Courier List

**Express/Same-Day Options**:
- Gojek - Same Day (Rp26,500) - 6-8 hours
- Gojek - Instant (Rp50,000) - 1-3 hours
- Grab - Instant (Rp52,000) - 1-3 hours
- Grab - Same Day (Rp17,000) - 6-8 hours

**Standard Options**:
- J&T - EZ (GRATIS/Free) - 3-4 days
- SiCepat - Regular (GRATIS/Free) - 2-3 days ✅ Currently Selected

### Selection Process

1. **View Couriers**: User sees all available options
2. **Compare**: Reviews price and delivery time
3. **Select**: Clicks radio button next to preferred courier
4. **Confirm**: Selection auto-confirms or explicit button pressed
5. **Return**: Returns to checkout page with new courier selected

### Pricing Variations

Courier prices vary based on:
- **Distance**: Farther distance = higher cost
- **Weight**: Heavier items = higher cost
- **Speed**: Express/same-day more expensive than standard
- **Area**: Red zones add surcharges
- **Promotions**: Seasonal discounts or promos

## Supported Couriers

### Gojek Family
- **Gojek - Instant**: 1-3 hours delivery, highest cost
- **Gojek - Same Day**: 6-8 hours delivery, medium cost

### Grab Express
- **Grab - Instant**: 1-3 hours delivery, highest cost
- **Grab - Same Day**: 6-8 hours delivery, medium cost

### Traditional Logistics
- **J&T Express**: 3-4 days standard delivery, low cost
- **SiCepat**: 2-3 days standard delivery, low/free cost
- **Pos Indonesia**: Government postal service, variable cost

### Regional Partners
- Various regional couriers for specific areas
- Prices and availability vary by location

## Delivery Time Options

### Speed Categories

**Instant Delivery** (1-3 hours)
- Most expensive option
- For urgent orders
- Limited availability (urban areas only)
- Requires order placed during courier operating hours

**Same-Day** (6-8 hours)
- Medium cost
- Order arrives same business day
- Available in most urban areas
- Courier picks up within 2 hours typically

**Next-Day** (1-2 days)
- Lower cost than same-day
- Standard for small packages
- Available nationwide
- Pickup typically within 24 hours

**Standard** (2-5 days)
- Lowest cost option
- Covers most of Indonesia
- For non-urgent shipments
- Reliable for general commerce

**Extended** (5-14 days)
- Very lowest cost
- Remote areas with limited access
- Red zone areas or archipelago regions
- Allow extra time in planning

## Price Display Logic

### Regular Pricing:
```
"Gojek - Same Day ( Rp26,500 )"
```
- Standard price, no discount
- Shown in single amount

### Promotional Pricing:
```
"Gojek - Same Day ( Rp36,500 Rp26,500 )"
```
- Original: Rp36,500 (struck through)
- Discounted: Rp26,500 (bold, new)
- Savings indicated visually

### Free Shipping:
```
"SiCepat - Regular ( Rp9,000 GRATIS )"
```
- Original: Rp9,000 (struck through)
- New: GRATIS (Free)
- Full discount applied

### Red Zone Surcharge:
```
"J&T - EZ ( Rp9,000 GRATIS + Rp5,000 Surcharge )"
```
- Base cost: GRATIS
- Red zone surcharge added
- Total shown to user

## Courier Availability by Location

### Coverage Map

Different couriers available in different regions:

**Jakarta & Major Cities**:
- ✅ All couriers available
- ✅ Gojek instant delivery available
- ✅ Most competitive pricing

**Secondary Cities**:
- ✅ Most couriers (J&T, SiCepat, Grab)
- ⚠️ Limited instant delivery
- ✅ Reasonable standard delivery costs

**Rural Areas**:
- ⚠️ Limited courier options
- ❌ No instant delivery
- ✅ Standard delivery still available

**Remote/Red Zone**:
- ⚠️ Very limited options
- ❌ No express services
- ⚠️ Higher costs + surcharges
- ⚠️ Extended delivery times

### Address-to-Courier Mapping

When user selects address:
- System checks postal code / coordinates
- System queries courier API for service areas
- System returns available couriers for that address
- System calculates cost for each
- System presents options to user

**If No Courier Available**:
- Error message shown
- User prompted to change address
- Contact support for remote areas option

## User Preferences & Behavior

### Types of Users

**Cost-Conscious Users**:
- Select free shipping option
- Accept longer delivery time
- Common for non-urgent items

**Speed-Focused Users**:
- Select instant/same-day delivery
- Accept higher cost
- Common for urgent orders

**Balanced Users**:
- Select standard (2-3 day) option
- Good cost/speed compromise
- Most common behavior

**Loyal to Courier**:
- Prefer specific courier brand
- May pay premium for preference
- Based on past experience

## Courier Selection Impact

### On Checkout Page:
```
Pilih Kurir: SiCepat - Regular (Rp11,000)
            Pengiriman (2-3) hari
```

Shows:
- ✅ Selected courier name
- ✅ Cost in Rupiah
- ✅ Estimated delivery duration

### On Order Summary:
- Courier cost added to "Subtotal Pengiriman" (Shipping Subtotal)
- Affects final total amount
- Shown before payment

### On Receipt/Confirmation:
- Courier displayed on order receipt
- Tracking number provided
- Delivery estimate confirmed

## Changing Courier

### Before Payment:
- ✅ User can click "Pilih Kurir" to open selection modal
- ✅ User can select different courier
- ✅ Price and delivery time update automatically
- ✅ Change reflected immediately on checkout page

### After Payment:
- ❌ Cannot change courier
- ⚠️ Contact merchant/support if urgent change needed
- ⚠️ Refund or modification may be possible

## Courier Tracking

### After Payment:
- Courier assigned after transaction confirmed
- Tracking number provided in confirmation email
- User can track package with:
  - Courier's tracking number
  - Merchant's tracking page
  - FLIK tracking system

### Tracking Features:
- Real-time location updates
- Delivery status notifications
- Estimated delivery window
- Contact courier option
- Package photo documentation

## Special Cases

### Merchant with Store Pickup Option

When merchant has pickup enabled:
- Courier selection only applies to "Kirim ke rumah" (Ship to home) tab
- Pickup option has no courier (user picks up directly)
- User chooses between delivery (requires courier) or pickup (no courier needed)

See: [Store Pickup Feature](./store-pickup.md)

### Bulk Orders

For large orders (varies by merchant):
- Special pricing may apply
- Limited courier options
- May require contact with merchant
- Can request bulk shipping quote

### COD (Cash on Delivery)

If merchant supports COD:
- Courier collects payment at delivery
- Limited to certain couriers (J&T, SiCepat, etc.)
- Additional COD fee may apply
- Cash only (no card/digital payment)

## API Reference (Developers)

### Get Available Couriers:
```
GET /checkout/couriers?address={address_id}&weight={weight}
```

Returns list of couriers with pricing:
```json
{
  "couriers": [
    {
      "id": "gojek_same_day",
      "name": "Gojek - Same Day",
      "cost": 26500,
      "originalCost": 36500,
      "deliveryTime": "6-8 hours",
      "isSelected": true,
      "logo": "url_to_logo"
    }
  ]
}
```

### Select Courier:
```
POST /checkout/courier-selection
{
  "courierId": "gojek_same_day",
  "checkoutSessionId": "session_123"
}
```

## Best Practices

### For Users:
1. ✅ **Check Delivery Time**: Ensure delivery fits your schedule
2. ✅ **Compare Costs**: See all options before selecting
3. ✅ **Consider Red Zone**: Budget for surcharges if applicable
4. ✅ **Track Package**: Use tracking number after payment
5. ✅ **Contact Early**: Alert courier if access issues expected

### For Developers:
1. ✅ **Cache Courier List**: Don't query API on every address change
2. ✅ **Validate Cost**: Re-validate cost before payment
3. ✅ **Handle Errors**: Show error if couriers unavailable
4. ✅ **Test All Couriers**: Test different address/weight combos
5. ✅ **Monitor Rates**: Courier rates change frequently

## Common Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| No couriers available | Address in restricted area | Try different address or contact support |
| Price different | Weight or address changed | Re-select courier to get new price |
| Instant delivery unavailable | Outside operating hours | Select same-day or next-day option |
| Courier not showing | API error or service issue | Refresh page or try again later |
| Can't change courier | Session expired | Re-load checkout page |

## Related Documentation

- [Address Management](./address-management.md) - Address affects courier availability
- [Store Pickup](./store-pickup.md) - Alternative to courier delivery
- [Payment Methods](./payment-methods.md) - Works with all payment methods

---

**Last Updated**: April 24, 2026  
**Version**: 1.0.0

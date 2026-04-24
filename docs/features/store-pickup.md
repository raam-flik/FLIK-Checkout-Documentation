# Store Pickup Feature

Complete guide to the offline store pickup option in FLIK Checkout.

## Overview

The **Store Pickup** feature allows merchants to offer customers an alternative to home delivery. Customers can pick up their purchases directly from the merchant's physical store location.

**Availability**: Optional - Only enabled by merchants who have physical stores

## Enabling Store Pickup

### For Merchants:
Store pickup must be enabled in merchant settings:
- Toggle: "Enable Store Pickup"
- Provide store locations
- Set store operating hours
- Configure pickup instructions

Once enabled, customers see tabbed interface to choose delivery method.

### Visual Indicator:
Merchants WITH pickup feature show tabbed interface:
- "Kirim ke rumah" (Ship to home) tab
- "Ambil di toko" (Pick up in store) tab

Merchants WITHOUT pickup feature only show standard delivery options.

## Checkout Page Variations

### Without Store Pickup (Standard Merchant):
Example: ZMNow merchant

**Desktop View**:
![Desktop Without Pickup](../../assets/screenshots/guest-checkout/Desktop%20-%202.png)

Shows only:
- Alamat Pengiriman (Delivery Address)
- Pilih Kurir (Select Courier)
- Metode Pembayaran (Payment Method)

### With Store Pickup (Merchant Enabled):
Example: Human Greatness merchant

**Desktop View** (Shipping Tab):
![Desktop With Pickup - Shipping](../../assets/screenshots/entry-point/Desktop%20-%202b.png)

**Desktop View** (Pickup Tab):
![Desktop With Pickup - Pickup](../../assets/screenshots/entry-point/Desktop%20-%202b.png)

Shows:
- **Two Tabs**:
  - "Kirim ke rumah" (Ship to home) - Default
  - "Ambil di toko" (Pick up in store)

## Switching Between Delivery Methods

### Tab Interface:

#### "Kirim ke rumah" (Ship to Home) Tab:
- Default tab when page loads
- Shows standard delivery flow
- Requires: Address, Courier, Payment Method
- Address field: "Alamat Pengiriman" (Delivery Address)

#### "Ambil di toko" (Pick up in Store) Tab:
- Alternative pickup option
- Shows store location selection
- No courier selection needed
- Address field changes to "Lokasi Toko" (Store Location)

### Switching Process:
1. User clicks "Ambil di toko" tab
2. Page refreshes to show pickup-specific fields
3. Address field replaced with store location selector
4. Courier section removed (not needed for pickup)
5. User selects store and proceeds to payment

## Store Location Selection

When user selects "Ambil di toko" tab, address field becomes store location field.

**Desktop View** (Location Selection Popup):
![Desktop Store Location](../../assets/screenshots/features/Desktop%20-%202ba.png)

**Mobile View** (Location Selection Popup):
![Mobile Store Location](../../assets/screenshots/features/MWeb%20-%202ba.png)

### Location Selection Modal:

#### Search/Find:
- **Search Field**: "Cari lokasi atau nama toko..." (Search location or store name)
- **Auto-complete**: Suggestions as user types
- **All Store Locations**: List of all available pickup locations

#### Store Information Displayed:
For each store location:
- **Store Name**: e.g., "Primary Warehouse"
- **Address**: Full store address
- **Hours of Operation** ("Jam Beroperasi"): e.g., "Thursday 08:00 - 17:00"
- **Map Link**: "Lihat di maps" (View on maps) to see store location

#### Example Store Details:
```
Primary Warehouse
Jl. Gandapura No.23, Merdeka, Kec. Sumur Bandung, Kota Bandung, Jawa Barat 40113, Indonesia

Jam Beroperasi:
Thursday 08:00 - 17:00
```

#### Selection:
- **Radio Button**: Select which store to pick up from
- **Only One**: Can only select one store
- **Confirm**: Click store or button to confirm selection

### Store Operating Hours:

Important considerations:
- Pickup only available during business hours
- Different stores may have different hours
- Closed on certain days/holidays
- User should check hours before scheduling pickup
- Instructions provided for after-hours pickup (if available)

## Pickup vs. Delivery Comparison

| Aspect | Ship to Home | Pick up in Store |
|--------|-------------|-----------------|
| **Location Selection** | Address entry required | Select from store list |
| **Courier** | Required, user selects | Not needed, pickup only |
| **Delivery Time** | 2-14 days typical | Same day or next day |
| **Delivery Cost** | Varies (Rp9k - Rp50k+) | Usually free or low cost |
| **Convenience** | Door-to-door | User must visit store |
| **Flexibility** | Flexible pickup window | Limited to store hours |
| **Contact Required** | Phone for delivery | User decides visit time |
| **Product Verification** | Post-delivery | Before pickup (recommended) |

## Pickup Process Flow

```
Select Items
    ↓
Click FLIK Button
    ↓
Login or Guest
    ↓
Checkout Page (Delivery/Pickup Tab)
    ↓
[SELECT "Ambil di toko"]
    ↓
Store Location Modal Opens
    ↓
Select Store from List
    ↓
Confirmation + Payment
    ↓
Select Payment Method
    ↓
Pay
    ↓
Order Confirmed - Pick up at store
```

## Checkout with Pickup

### Pickup Checkout Page:

After selecting store:
- ✅ Contact Information: Complete (name, email)
- ✅ Store Location: Selected and displayed
- ❌ Courier: Not shown/needed
- ❌ Delivery Address: Replaced with store location
- ❌ Metode Pembayaran: Still required

**Important Differences**:
- No shipping cost added
- No courier selection step
- Faster checkout than delivery
- Less information required

### Order Summary:
```
Subtotal: Rp143,000
Subtotal Pengiriman: Rp0 (No shipping cost)
Total: Rp143,000
```

## Pickup Instructions

### After Purchase:
Customer receives order confirmation with:
1. **Order Number**: For reference
2. **Store Location**: Where to pick up
3. **Store Hours**: When store is open
4. **Contact Number**: Store phone number
5. **Special Instructions**: Any special pickup requirements

### Pickup Window:
- **Typical**: Same day or next business day
- **Notice**: Email/SMS notification when ready
- **Hold Period**: Item held for X days (e.g., 7 days)
- **Contact**: Call store if need to arrange later pickup

### At Pickup:
1. Arrive at store during operating hours
2. Provide order number
3. Staff retrieves item
4. Verify item condition
5. Complete pickup (sign receipt if required)
6. Take item

## Payment During Pickup Checkout

Payment works same as delivery:
- User selects payment method
- All methods available (e-wallet, QRIS, VA, etc.)
- Instant payment required
- Receipt confirmation sent via email

**Note**: No COD (Cash on Delivery) option for pickup - payment required at checkout.

## Store Pickup Benefits

### For Customers:
- ✅ Lower shipping cost (free or minimal)
- ✅ Faster fulfillment (same-day possible)
- ✅ No need to provide address
- ✅ Immediate product verification
- ✅ Direct merchant communication possible
- ✅ Privacy (no courier knows home address)

### For Merchants:
- ✅ Lower fulfillment cost (no courier needed)
- ✅ Reduced shipping overhead
- ✅ Store foot traffic increase
- ✅ Customer relationship building
- ✅ Reduced delivery-related complaints
- ✅ Return/exchange easier (customer on-site)

## Store Pickup Limitations

### Availability:
- ❌ Not available for merchants without physical stores
- ❌ Not available at all store locations (merchant choice)
- ⚠️ Limited pickup hours (store operating hours only)

### Product Limitations:
- Some items may not be eligible for pickup
- Bulky items may require special handling
- Perishables may have restrictions
- Hazardous items may have legal restrictions

### Customer Limitations:
- ⚠️ Must physically visit store (not convenient for remote users)
- ⚠️ Limited to store operating hours
- ⚠️ No payment plans (full upfront payment)
- ⚠️ No COD option

## Technical Implementation

### For Developers:

#### Get Store Locations:
```
GET /merchants/{merchantId}/stores
```

Returns:
```json
{
  "stores": [
    {
      "id": "store_123",
      "name": "Primary Warehouse",
      "address": "Jl. Gandapura No.23...",
      "latitude": -6.297,
      "longitude": 106.815,
      "operatingHours": {
        "monday": "08:00-17:00",
        "tuesday": "08:00-17:00",
        "...": "..."
      },
      "phone": "+621234567890"
    }
  ]
}
```

#### Save Pickup Selection:
```
POST /checkout/store-pickup
{
  "checkoutSessionId": "session_123",
  "storeId": "store_123"
}
```

## API Integration

### Pickup-Specific Endpoints:
- `GET /merchants/{id}/stores` - List pickup locations
- `POST /checkout/select-store` - Select store for pickup
- `GET /checkout/validate-store-pickup` - Validate pickup method
- `POST /orders/{id}/pickup-notification` - Send pickup ready notification

## Related Documentation

- [Address Management](./address-management.md)
- [Courier Selection](./courier-selection.md)
- [Merchant Configurations](./merchant-configurations.md)

---

**Last Updated**: April 24, 2026
**Version**: 1.0.0

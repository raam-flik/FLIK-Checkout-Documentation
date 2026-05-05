# Address Management Feature

Complete guide to address selection, entry, validation, and management in FLIK Checkout.

## Overview

The **Address Management** feature allows users to:
- **Add New Address**: Enter delivery address with map integration
- **Select Saved Address**: Choose from previously saved addresses (registered users)
- **Edit Address**: Modify existing saved addresses
- **Delete Address**: Remove addresses from saved list
- **Map Integration**: Pinpoint exact location using interactive map
- **Validation**: Auto-check address against delivery coverage areas

## Address Entry Modal

### Map-Based Address Selection

Users can locate their address using:

1. **Search Field**: Type address or location name
2. **Interactive Map**: Drag marker to exact location
3. **Google Maps Integration**: View actual maps and landmarks
4. **Auto-complete**: Suggested addresses as user types

**Desktop View**:
![Desktop Address Entry](../../assets/screenshots/features/Desktop%20-%206.png)

**Mobile Web View**:
![Mobile Address Entry](../../assets/screenshots/features/MWeb%20-%206.png)

### Modal Structure

#### Recipient Information:
- **Nama Penerima** (Recipient Name)
  - Default: Pre-filled with user's name
  - Editable: User can change if needed
  - Required: Must not be empty

- **HP Penerima** (Recipient Phone)
  - Format: Must include country code (+62 for Indonesia)
  - Required: Must be valid phone number
  - Validation: System checks format
  - Error Message: "Isi Nomor Handphone yang valid" if incorrect

#### Location Search & Map:
- **Search Field**: "Type Location, Place, Apartment, Building"
  - Placeholder helps user understand what to enter
  - Auto-complete suggestions appear as user types
  - Search queries checked against Google Maps data

- **Interactive Map**:
  - Shows current location (blue area) and nearby landmarks
  - Red marker shows selected location
  - User can **drag marker** to adjust location
  - Instruction: "Drag marker atau cari alamat" (Drag marker or search address)
  - **"Lihat di maps"** (View on maps) button opens full Google Maps view

#### Address Details:
- **Alamat** (Address) - Text Area
  - Full street address
  - Pre-filled from map selection if available
  - User can edit or add details
  - Multi-line input for longer addresses

- **Detail Alamat** (Address Details) - Placeholder
  - Additional details: Gedung, Lantai, RT/RW, etc.
  - Building, Floor, RT/RW (neighborhood codes)
  - Apartment/Unit number
  - Help text guides user on what to include

- **Autofill** - Dropdown
  - Optional auto-fill suggestion
  - Can be ignored or selected

- **Kode Pos** (Postal Code) - Text Field
  - ZIP/Postal code
  - Used for area/red zone verification
  - Required for accurate delivery routing

#### Action Button:
- **Simpan** (Save) - Primary Button
  - Saves address to user's saved addresses list
  - Returns to checkout page with address selected
  - For new addresses, adds to user's address book
  - For edited addresses, updates existing entry

### Address Validation

System performs automatic validation:

✅ **Format Checks**:
- Phone number format (must be valid)
- Postal code format (must be valid)
- Address not empty

✅ **Coverage Checks**:
- Address within service area
- Postal code matches address
- City/Province valid

✅ **Red Zone Detection**:
- Address in "red zone" (restricted area)?
- If yes, shows warning with additional costs
- User can proceed despite red zone

❌ **Error Handling**:
- Invalid phone number: Error message with red highlight
- Incomplete address: Error on save attempt
- Out of service area: Warning message with options

### Recipient Details - Phone Number Format

**Indonesia Phone Number Example**:
- Country Code: +62
- Area/Mobile Code: 85 (for mobile numbers)
- Number: 159852622
- **Full**: +6285159852622

**System Requirements**:
- Always include +62 for Indonesia
- Can handle other country codes for international addresses
- Validation checks format before saving

## Saved Address List (Registered Users)

### Desktop View:
![Desktop Saved Address List](../../assets/screenshots/features/Desktop%20-%209.png)

### Mobile Web View:
![Mobile Saved Address List](../../assets/screenshots/features/MWeb%20-%209.png)

### Address List Modal

#### Modal Title:
- **"Alamat Pengiriman"** (Delivery Address)
- **Helper Text**: "Centang alamat sebagai default" (Check address as default)

#### Address Display:
Each saved address shows:
- **Address Label**: Name and phone number on first line
  - Example: "Tukla Kuy | +62851598852622"
  - Allows user to quickly identify address

- **Full Address**: Complete address on second+ lines
  - Full street address
  - Building/apartment details
  - City and postal code
  - Complete information shown

- **Default Indicator**: Radio button or checkmark
  - Shows which address is set as primary default
  - Used for future purchases if not changed
  - Only one address can be default

#### Address Actions:
- **Ubah** (Edit) Button
  - Opens address entry modal with current data
  - Allows modification of any field
  - Must click "Simpan" to save changes

- **Hapus** (Delete) Button
  - Removes address from saved addresses
  - Confirmation may be required
  - Cannot delete current/active address during checkout

#### Add New Address:
- **"+ Tambah Alamat"** Button at bottom
- Opens address entry modal (see above)
- Adds new address to saved list
- User can immediately select new address

### Address Selection Process

1. **View List**: User sees all saved addresses
2. **Select**: Click on address or radio button to select
3. **Make Default** (Optional): Check radio button to set as default for future purchases
4. **Confirm**: Selection immediately updates checkout page
5. **Alternative**: Click "Tambah Alamat" to add new address

## Address Usage in Checkout

### Guest Users:
- ✅ Can **add new address** during checkout
- ❌ Cannot save address for future use (no account)
- ✅ Address used for current transaction only
- ⚠️ If re-checkout as guest, must re-enter address

### Registered Users:
- ✅ Can **select from saved addresses**
- ✅ Can **add new address** and save for future use
- ✅ Address auto-filled on future purchases
- ✅ Can edit or delete saved addresses
- ✅ Can set default address for quick future checkouts

## Address Impact on Courier Selection

### Courier Availability:
- **Different addresses** may have different available couriers
- Some couriers may not serve certain areas
- Address selection triggers courier re-evaluation

### Auto-Selection Logic:
When address is selected/changed:
1. System validates address
2. System checks which couriers serve that area
3. System selects **cheapest option automatically**
4. User can see alternatives and choose different courier

### Example:
- **Address 1** (Jakarta City): Gojek, Grab, J&T, SiCepat available, Cheapest = Rp11,000 (SiCepat)
- **Address 2** (Bogor Outskirts): Grab, J&T available (no Gojek), Cheapest = Rp15,000 (J&T)
- **Address 3** (Remote Area - Red Zone): J&T only, Rp35,000 + 20% surcharge

## Red Zone Information

### What is Red Zone?
Areas with delivery challenges including:
- Remote locations
- Difficult access
- Limited courier coverage
- Natural disaster-prone areas
- Restricted zones

### Red Zone Impact:
- **Extended Timeline**: Delivery takes 5-10+ days (vs. normal 1-3 days)
- **Additional Cost**: 20-50%+ surcharge applied to base shipping cost
- **Limited Couriers**: Fewer courier options available
- **Manual Processing**: May require special handling

### Red Zone Detection:
- System **automatically detects** when address is in red zone
- Warning message shown with additional cost breakdown
- User can **proceed with acknowledgment** or **select different address**
- Extra cost clearly displayed before payment

### Example Red Zone Pricing:
```
Base shipping cost: Rp25,000
Red zone surcharge: +Rp5,000 (20%)
Total: Rp30,000

Or

Base shipping cost: Rp25,000
Red zone surcharge: +Rp12,500 (50%)
Total: Rp37,500
```

## Address Validation Errors

### Common Validation Issues:

| Error | Cause | Solution |
|-------|-------|----------|
| "Isi Nomor Handphone yang valid" | Invalid phone format | Re-enter phone with +62 format |
| "Alamat belum valid" | Address not recognized | Search more specifically or use map |
| "Kode Pos tidak sesuai" | Postal code doesn't match address | Verify postal code is correct |
| "Area tidak terjangkau" | Address outside service area | Check if area is serviced by any courier |
| "Alamat terlalu singkat" | Address too brief | Add more detail (street, number, area) |

## Address Security & Privacy

### Data Protection:
- ✅ Addresses stored encrypted in database
- ✅ Only shared with delivery partners when needed
- ✅ User can delete saved addresses anytime
- ✅ Address data compliant with GDPR and local privacy laws

### Who Can Access:
- ✅ User (own account)
- ✅ FLIK system (for delivery routing)
- ✅ Selected courier (only for that shipment)
- ❌ Public or other users (never exposed)

## Best Practices

### For Users:
1. ✅ **Be Specific**: Include building/apartment number
2. ✅ **Use Map**: Pinpoint exact location, not just street
3. ✅ **Save Multiple**: Add home, office, family locations
4. ✅ **Keep Updated**: Update addresses when you move
5. ✅ **Include Landmarks**: "Near market" or "Behind cafe" helps courier

### For Address Accuracy:
1. ✅ **Full Details**: Don't abbreviate (Jalan = Jl., Kompleks = Komp.)
2. ✅ **RT/RW**: Include neighborhood codes if in Jakarta
3. ✅ **Phone Verification**: Make sure phone number is reachable
4. ✅ **Name Accuracy**: Use name courier will call

### For Red Zone Avoidance:
1. ✅ **Check Early**: Verify address before committing to purchase
2. ✅ **Have Alternatives**: Save multiple addresses in different areas
3. ✅ **Consider Costs**: Budget for surcharge in red zones
4. ✅ **Plan Timeline**: Allow extra time for red zone deliveries

## Integration with Other Features

### Works With:
- **Courier Selection**: Address determines available couriers
- **Red Zone Check**: Address validated for delivery feasibility
- **Payment Methods**: No direct impact
- **Discounts**: No direct impact
- **Rewards**: No direct impact

### Related Features:
- See [Courier Selection](./courier-selection.md) - Courier availability depends on address
- See [Store Pickup](./store-pickup.md) - Alternative to address delivery

## Address Management API (For Developers)

### Key Endpoints:
- `GET /addresses` - List saved addresses
- `POST /addresses` - Add new address
- `PATCH /addresses/{id}` - Update address
- `DELETE /addresses/{id}` - Delete address
- `POST /addresses/validate` - Validate address

### Address Object Structure:
```json
{
  "id": "addr_123",
  "recipientName": "Raam Pujangga Sadewa",
  "phone": "+6281718544811",
  "street": "Pusat Niaga Duta Mas Lt. 2 Blok E",
  "details": "No. 28 & 21",
  "city": "Jakarta",
  "province": "DKI Jakarta",
  "postalCode": "12520",
  "country": "Indonesia",
  "latitude": -6.2971,
  "longitude": 106.8151,
  "isDefault": true,
  "isRedZone": false,
  "createdAt": "2026-04-15T10:30:00Z",
  "updatedAt": "2026-04-24T14:20:00Z"
}
```

## Troubleshooting

### Address Not Showing After Save:
- Refresh page to reload saved addresses
- Check if address was actually saved (confirm message)
- Verify internet connection stable during save

### Courier Not Available for Address:
- Address may be in restricted delivery area
- Too remote for current available couriers
- Try different address nearby
- Contact support for remote area options

### Red Zone Warning:
- Address confirmed in restricted area
- Accept additional surcharge to proceed
- Or select different address
- Check FLIK coverage map for alternatives

---

**Last Updated**: April 24, 2026  
**Version**: 1.0.0

# FLIK Checkout Integration Guide

Quick start guide for integrating FLIK Checkout on your website.

## Integration Overview

FLIK Checkout can be integrated into any e-commerce website in minutes using our embed code or API.

### Two Integration Methods:

1. **Widget/Embed** (Easiest)
   - Copy-paste one line of code
   - Works on any website
   - No backend required
   - Hosted by FLIK

2. **API Integration** (Advanced)
   - Full control
   - Custom implementation
   - Requires backend
   - Webhooks for events

## Quick Start (Widget Method)

### Step 1: Generate Your Button Code

1. Login to FLIK Merchant Dashboard
2. Navigate to "FLIK Checkout Setup"
3. Click "Generate Button Code"
4. Configure button appearance (optional)
5. Copy generated code

### Step 2: Add to Your Website

Add this line to your checkout page (before </body>):

```html
<script src="https://cdn.flik.co.id/checkout.js"></script>
<button onclick="window.FLIK.openCheckout('merchant_YOUR_ID');" 
        class="flik-button">
  💳 FLIK Buy it now
</button>
```

Or for product pages:

```html
<button onclick="window.FLIK.openCheckout({
  merchantId: 'merchant_YOUR_ID',
  amount: 143000,
  currency: 'IDR'
});" class="flik-button">
  💳 FLIK Buy it now
</button>
```

### Step 3: Test

1. Click button on your website
2. Complete test checkout
3. Verify order appears in FLIK dashboard
4. Confirm email notifications working

## Button Placement

### Recommended Locations:
- ✅ Product page (next to "Add to Cart")
- ✅ Cart page (next to "Checkout")
- ✅ Confirmation page (alternative payment)
- ✅ Shipping form (embedded in form)

### Styling Options:
```html
<!-- Dark theme -->
<button class="flik-button flik-dark">💳 FLIK Buy it now</button>

<!-- Light theme -->
<button class="flik-button flik-light">💳 FLIK Buy it now</button>

<!-- Minimal -->
<button class="flik-button flik-minimal">FLIK</button>

<!-- Custom -->
<button style="padding: 10px 20px; background: #FF6B35; color: white;">
  💳 Quick Checkout
</button>
```

## Webhook Configuration

### Setup Webhooks:

1. Dashboard → Settings → Webhooks
2. Enter webhook URL: `https://yoursite.com/flik-webhook`
3. Select events to subscribe
4. Test webhook delivery

### Events:
- `checkout.completed` - Payment successful
- `checkout.failed` - Payment failed
- `order.confirmed` - Order confirmed
- `order.shipped` - Order shipped
- `order.delivered` - Order delivered

### Webhook Payload Example:
```json
{
  "event": "checkout.completed",
  "transactionId": "23042026-DIVUXH",
  "amount": 154000,
  "currency": "IDR",
  "status": "completed",
  "customerId": "customer_123",
  "timestamp": "2026-04-23T19:45:00Z"
}
```

## API Integration

### Authentication:
```
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

### Create Checkout Session:
```
POST https://api.flik.co.id/v1/checkout
{
  "merchantId": "merchant_YOUR_ID",
  "amount": 143000,
  "currency": "IDR",
  "orderRef": "ORDER_123",
  "customerEmail": "user@example.com",
  "items": [
    {
      "name": "Martes Os T-Shirt",
      "price": 143000,
      "quantity": 1
    }
  ],
  "successUrl": "https://yoursite.com/success",
  "failureUrl": "https://yoursite.com/failed",
  "metadata": {
    "customField": "customValue"
  }
}
```

### Response:
```json
{
  "checkoutUrl": "https://checkout.flik.co.id/session_abc123",
  "sessionId": "session_abc123",
  "expiresAt": "2026-04-23T20:45:00Z"
}
```

## Testing

### Test Credentials:

**Test OTP Code**: Always use `000000` for testing

**Test Payment Methods**:
- QRIS: Always succeeds in test mode
- Virtual Account: Use any account
- E-Wallets: Auto-approves in test

### Test Scenarios:

1. **Guest Checkout**
   - New customer without account
   - Go through full flow
   - Verify email received

2. **Registered User**
   - Login with test phone
   - Verify pre-filled data
   - Test with different address

3. **Failure Cases**
   - Invalid payment info
   - Expired session
   - Unsupported address

## Environment Setup

### Development:
```
API_BASE: https://dev-api.flik.co.id
CHECKOUT_URL: https://dev-checkout.flik.co.id
MODE: sandbox
```

### Production:
```
API_BASE: https://api.flik.co.id
CHECKOUT_URL: https://checkout.flik.co.id
MODE: live
```

## Troubleshooting

### Button not appearing
- Check script tag loaded properly
- Verify merchant ID is correct
- Check browser console for errors

### Checkout not opening
- Verify button click handler
- Check merchant configuration
- Test with example merchant ID

### Payment declined
- Check payment method enabled in merchant config
- Verify amount is not below minimum
- Check if address in red zone

### Webhook not firing
- Verify webhook URL is public
- Check webhook logs in dashboard
- Verify event subscription enabled

## Security Best Practices

### Frontend:
- ✅ Always use HTTPS
- ✅ Never hardcode sensitive keys in frontend
- ✅ Validate responses on your backend
- ✅ Implement CSRF protection

### Backend:
- ✅ Validate webhook signatures
- ✅ Keep API keys secret
- ✅ Use environment variables
- ✅ Implement rate limiting
- ✅ Log all transactions

### PCI Compliance:
- ✅ Never store card data
- ✅ Use FLIK tokenized payments
- ✅ Implement SSL/TLS
- ✅ Regular security audits

## Support & Resources

- **Documentation**: https://docs.flik.co.id
- **API Reference**: https://api-docs.flik.co.id
- **Dashboard**: https://merchant.flik.co.id
- **Support Email**: support@flik.co.id
- **Community**: https://community.flik.co.id

---

**Last Updated**: April 24, 2026
**Version**: 1.0.0

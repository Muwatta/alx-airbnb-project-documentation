## File: requirements.md

# Requirement Specifications — Airbnb Backend

This file documents technical requirements for core features.

## 1. User Authentication

### Endpoints
POST /api/auth/register
POST /api/auth/login
GET  /api/auth/profile
PUT  /api/auth/profile
DELETE /api/auth/delete

### Request Validation
- Email must be RFC-compliant and unique
- Password must be ≥ 8 characters and include letters and numbers
- Name (optional) max 100 chars

### Security
- Store passwords hashed with bcrypt (salt rounds: 12)
- Use HTTPS for all endpoints

### Response
Success (201):
{
  "id": 1,
  "email": "user@example.com",
  "token": "jwt-token"
}

### Performance
- Average auth request < 300ms under normal load

---

## 2. Property Management

### Endpoints
POST /api/properties
GET  /api/properties
GET  /api/properties/:id
PUT  /api/properties/:id
DELETE /api/properties/:id

### Validation
- title: required, max 150 chars
- price: required, number >= 0
- location: required
- images: array of URLs or uploaded files

### Notes
- Images should be uploaded to object storage and stored as URLs.
- Implement pagination for GET /api/properties (limit, page) and filtering query params.

---

## 3. Booking System

### Endpoints
POST /api/bookings
GET  /api/bookings
GET  /api/bookings/:id
PUT  /api/bookings/:id/approve
PUT  /api/bookings/:id/reject

### Validation
- start_date and end_date required and ISO format
- end_date > start_date
- booking must not overlap existing approved bookings for the same property

### Business Logic
- total_price = nights × property.price + platform_fees
- On booking request: create booking with status 'pending'
- Host can approve -> status 'approved' (then charge or capture payment depending on workflow)

---

## 4. Payments (Stripe)

### Endpoints
POST /api/payments/checkout
POST /api/payments/webhook (Stripe webhook)

### Flow
1. Create checkout session with Stripe for booking amount.
2. Redirect user to Stripe checkout.
3. Stripe sends webhook on payment success -> update payments DB and booking status.

### Security
- Verify Stripe webhook signatures

---

## Example Database Schema (simplified)

users(id, email, password_hash, name, role, created_at)
properties(id, host_id, title, description, price, location, images_json, created_at)
bookings(id, property_id, guest_id, start_date, end_date, total_price, status, created_at)
payments(id, booking_id, stripe_charge_id, amount, status, created_at)


# ALX Airbnb Project Documentation — Ready Deliverables

## File: features-and-functionalities/README.md


# Airbnb Backend — Features & Functionalities

This document outlines the core backend features required to power an Airbnb-style booking platform.

## 1. User Authentication & Management
- Register account
- Login with email + password
- JWT-based authentication
- Update user profile
- Upload profile photo
- Delete account
- Password reset (email)
- Role management (guest, host, admin)

## 2. Property Listings Management
- Host can create property listings
- Add property details (title, description, price, location, amenities)
- Upload multiple images
- Update property details
- Delete listing
- Drafts and publish states
- Search/filter listings by:
  - Location
  - Price range
  - Number of rooms
  - Property type
  - Amenities
  - Availability dates

## 3. Booking System
- User can request bookings
- Host can approve/reject bookings
- Guests receive booking confirmation
- Users can view booking history
- Auto-calculate total cost (nights × price + fees)
- Prevent double-booking
- Date availability calendar
- Booking cancellations & refund policies
- Notifications (email/websocket) for important events

## 4. Payments
- Integration with Stripe (or PayPal)
- Create checkout session and confirm payment
- Webhook handling for payment events
- Capture payments and issue refunds
- Store transactional records in Payments table

## 5. Reviews & Ratings
- Guests can leave reviews for properties
- Star rating system
- Hosts can reply to reviews
- Aggregate rating computed for listings

## 6. Admin Functionality
- View all users
- Deactivate or remove user accounts
- View all properties
- Remove or flag inappropriate listings
- Access system logs / audit trail

## 7. Extra / Optional Features
- Saved favorites / wishlists
- Host verification (ID upload)
- Messaging between guest and host
- Image optimization & CDN
- Rate limiting and basic abuse prevention









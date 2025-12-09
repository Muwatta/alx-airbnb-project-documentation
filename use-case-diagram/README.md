## File: use-case-diagram/README.md

# Use Case Diagram — Instructions

Draw a Use Case diagram (use Draw.io / Diagrams.net). Export a PNG to this folder.

Actors:
- Guest
- Host
- Admin
- Payment Gateway (external system)

Use Cases grouped by actor:

Guest:
- Register / Login
- Search properties
- View property details
- Request booking
- Make payment
- Cancel booking
- Leave review

Host:
- Register / Login
- Create listing
- Update listing
- Upload images
- View booking requests
- Approve / Reject booking
- Manage calendar availability

Admin:
- Login
- Manage users
- Manage listings
- View reports

Payment Gateway:
- Process payment
- Send webhook events (payment_success, refund)


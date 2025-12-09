## File: data-flow-diagram/README.md

# Data Flow Diagram — Instructions

Create a Level-1 Data Flow Diagram using Draw.io. Save as data-flow.png in this folder.

Entities:
- Guest (external)
- Host (external)
- Stripe (external)

Processes:
1. User Management
2. Property Management
3. Booking Management
4. Payment Processing

Data Stores:
- users (Users table)
- properties (Listings table)
- bookings (Bookings table)
- payments (Payments table)

Key flows:
- Guest submits registration => User Management => users DB
- Host adds property => Property Management => properties DB
- Guest requests booking => Booking Management => bookings DB
- Guest pays => Payment Processing => Stripe => payments DB


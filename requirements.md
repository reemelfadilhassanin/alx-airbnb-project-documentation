# Backend Feature Requirements

## User Authentication

- **POST /api/auth/register**

  - Input: { first_name, last_name, email, password }
  - Validation: email unique, password min 8 chars
  - Output: success message, JWT token
- **POST /api/auth/login**

  - Input: { email, password }
  - Output: JWT token, user role

## Property Management

- **POST /api/properties**
  - Auth: host only
  - Input: { name, description, location, pricepernight }
  - Output: created property

## Booking System

- **POST /api/bookings**
  - Input: { property_id, start_date, end_date }
  - Validation: no overlap
  - Output: booking with pending status

## Payments

- **POST /api/payments**
  - Input: { booking_id, amount, method }
  - Output: payment record, booking status confirmed

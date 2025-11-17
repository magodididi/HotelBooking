# HotelBookingV2 - Domain Model Class Diagram

## Overview
This document describes the key entities and their relationships within the **HotelBookingV2** application domain, based on the database schema and system design. This model serves as a conceptual foundation for the system’s object-oriented implementation and database structure.

## Class Diagram Schema

![Class Diagram](./docs/schema/hotelbookingv2_uml.png)

## Class Diagram Description
The core domain of **HotelBookingV2** revolves around users, accounts, hotels, rooms, bookings, and preferences. The main entities are:

* **`User`**: Represents the system user with authentication credentials.
* **`Account`**: Represents detailed user information and preferences.
* **`Hotel`**: Represents a hotel entity with available rooms and facilities.
* **`Room`**: Represents a hotel room and its characteristics.
* **`Booking`**: Represents a reservation made by a user for a specific room.
* **`Facility`**: Represents amenities or facilities that can be associated with rooms.
* **`Likes`**: Represents user preferences for hotels or rooms.

### Key Relationships Explained:

1. **User - Account (One-to-One)**:
    * Each `User` has exactly one `Account`.
    * Each `Account` is linked to a single `User`.

2. **Account - Likes (One-to-Many)**:
    * An `Account` can like multiple hotels or rooms.
    * Each `Likes` entry belongs to a single `Account`.

3. **Booking - Room / Account / Hotel (Many-to-One)**:
    * A `Booking` is associated with a single `Room`, `Hotel`, and `Account`.
    * Each `Room` and `Hotel` can have multiple `Booking` entries.

4. **Hotel - Room (One-to-Many)**:
    * A `Hotel` contains multiple `Room` entities.
    * Each `Room` belongs to a single `Hotel`.

5. **Room - Facility (Many-to-Many)**:
    * A `Room` can have multiple `Facility` entities.
    * Each `Facility` can belong to multiple rooms.
    * Implemented via a junction table `room_facilities`.

### Attributes:

* **`User`**: `id` (PK), `username`, `email`, `password`.
* **`Account`**: `id` (PK), `full_name`, `birth_date`, `passport_number`, `phone`, `preferred_hotel_category`, `preferred_room_type`, `user_id` (FK to User).
* **`Hotel`**: `id` (PK), `name`, `city`, `category`, `available_from_date`.
* **`Room`**: `id` (PK), `room_number`, `type`, `price`, `hotel_id` (FK to Hotel).
* **`Booking`**: `id` (PK), `check_in_date`, `check_out_date`, `guest_full_name`, `guest_passport_number`, `guest_passport_series`, `guest_phone`, `payment_status`, `status`, `total_price`, `account_id` (FK to Account), `hotel_id` (FK to Hotel), `room_id` (FK to Room).
* **`Facility`**: `id` (PK), `name`.
* **`Likes`**: `id` (PK), `liked`, `account_id` (FK to Account), `hotel_id` (FK to Hotel, optional), `room_id` (FK to Room, optional).

This model ensures clear separation between users and their accounts, flexible booking management, and support for user preferences and likes.


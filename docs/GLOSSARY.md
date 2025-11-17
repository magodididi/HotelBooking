# HotelBookingV2 - Glossary of Key Terms

## Account (User Account)
A unique identity within the HotelBookingV2 system, created during registration. It is associated with a user's personal data, booking history, and list of favorites.

## Authentication
The process of verifying a user's identity, typically by validating a username and password combination. Successful authentication results in the issuance of a session token (JWT).

## Authorization
The process of determining and enforcing what actions an authenticated user is permitted to perform (e.g., making a booking, viewing personal statistics, managing favorite items).

## Booking
A reservation of a specific room by a user for a defined period of time.

## Controller
A component that provides the REST API interface, handling incoming client requests, invoking business logic, and returning responses.

## DTO (Data Transfer Object) / Mapper
A pattern used to transfer data between software application subsystems. DTOs are simple objects that carry data between processes (e.g., between a controller and a service), while Mappers handle the conversion between entities and DTOs.

## Facility
An amenity or service provided by a hotel to enhance a guest's stay (e.g., Wi-Fi, air conditioning, swimming pool).

## Favorite / Like
A marker set by a user to indicate a preferred hotel or room type, which is then saved to their personal account for easy access.

## Hotel
A property available for booking, characterized by its description, location, list of available rooms, and facilities.

## JWT (JSON Web Token)
A compact, URL-safe means of representing claims to be transferred between two parties. In HotelBookingV2, it is used as a session token to prove a user's authenticated state without repeatedly sending credentials.

## Room
An individual accommodation unit within a hotel, defined by its type, capacity, price, and current availability status.

## Service
A component that encapsulates the core business logic of the application, operating on entities and DTOs to perform specific operations.

## Statistics
Data aggregated and analyzed for the administration dashboard, providing insights into booking trends, hotel performance, and user behavior.

## User
A registered individual who interacts with the HotelBookingV2 system. Can assume different roles, such as customer, administrator, or employee, which determine their permissions.

## Payment API / External Service
A third-party service that handles payments for bookings securely. Interactions typically include authorization, capture, and refunds.

## Notification Service
A component responsible for sending transactional notifications, such as booking confirmations or updates, via email or SMS.



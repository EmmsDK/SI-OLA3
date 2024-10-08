# Strategic Design

## Link til video:
- https://www.youtube.com/watch?v=ColtlF4bKyA

## Bounded Contexts
We will divide the system into the following bounded contexts:

- **Booking Context**: Handles trailer reservations.
- **Insurance Context**: Manages trailer insurance.
- **Late Fee Context**: Deals with penalties for late trailer returns.
- **Partnership Context**: Manages relationships with partners (stores like Jem og Fix).

## Ubiquitous Language
It's important to define a consistent language across the project:

- **Trailer**: A rentable vehicle unit.
- **Customer**: A person using the app to book trailers.
- **Partner**: A store providing space for the trailer (e.g., Jem og Fix).
- **Booking**: The process of reserving a trailer for a specified time.
- **Insurance**: Optional coverage bought by the customer when renting a trailer.
- **Late Fee**: Penalty for returning a trailer past the agreed time.

# Tactical Design

## Aggregates
Each context has key aggregates:

### Booking Context
- **Entities**: Customer, Trailer, Booking
- **Value Objects**: Location, Trailer ID

### Insurance Context
- **Entities**: InsurancePolicy, Customer
- **Value Objects**: PolicyTerms, CoverageAmount

### Late Fee Context
- **Entities**: LateFee, Booking

### Partnership Context
- **Entities**: Partner, Trailer
- **Value Objects**: Location, Advertisement

## Entities and Value Objects

### Booking Entity
- **Properties**: Booking ID, Customer ID, Trailer ID, Start Time, End Time, Booking Status

### Trailer Entity
- **Properties**: Trailer ID, Location, Status

### Customer Entity
- **Properties**: Customer ID, Name, Email, Payment Information

### InsurancePolicy Entity
- **Properties**: Policy ID, Customer ID, Coverage Amount, Terms

## Repositories

- **BookingRepository**: Handles CRUD operations related to bookings.
- **InsuranceRepository**: Manages insurance policies.
- **LateFeeRepository**: Tracks and calculates late fee penalties.
- **PartnerRepository**: Manages the partnership agreements.

## Services

- **BookingService**: Contains logic for trailer bookings, including validation and availability checks.
- **InsuranceService**: Handles the purchase of insurance for trailers.
- **LateFeeService**: Calculates late fees when a trailer is returned past the due time.
- **PartnerService**: Manages the business logic related to trailer locations and partner agreements.

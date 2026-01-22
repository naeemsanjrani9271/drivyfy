# Database Schema

## Users Table
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| id          | INT       | Primary Key |
| name        | VARCHAR   | User's name |
| email       | VARCHAR   | User's email (unique) |
| password    | VARCHAR   | User's password |
| created_at  | TIMESTAMP | User creation timestamp |

## Rides Table
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| id          | INT       | Primary Key |
| user_id     | INT       | Foreign Key referencing Users |
| origin      | VARCHAR   | Ride origin location |
| destination | VARCHAR   | Ride destination location |
| date        | DATE      | Ride date |
| created_at  | TIMESTAMP | Ride creation timestamp |

## Bookings Table
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| id          | INT       | Primary Key |
| user_id     | INT       | Foreign Key referencing Users |
| ride_id     | INT       | Foreign Key referencing Rides |
| booking_date | TIMESTAMP | Booking date and time |
| status      | VARCHAR   | Booking status (e.g., confirmed, cancelled) |

## Reviews Table
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| id          | INT       | Primary Key |
| user_id     | INT       | Foreign Key referencing Users |
| ride_id     | INT       | Foreign Key referencing Rides |
| rating      | INT       | Rating given by the user |
| comment     | TEXT      | Review comment |
| created_at  | TIMESTAMP | Review creation timestamp |
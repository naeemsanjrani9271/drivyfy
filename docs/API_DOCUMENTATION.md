# API Documentation

## Authentication

### Login
- **Endpoint**: `/api/v1/auth/login`
- **Method**: POST
- **Request Body**:
  - `username`: String (required)
  - `password`: String (required)
- **Response**:
  - **200 OK**: 
    - `token`: String
  - **401 Unauthorized**: 
    - `message`: String

### Register
- **Endpoint**: `/api/v1/auth/register`
- **Method**: POST
- **Request Body**:
  - `username`: String (required)
  - `email`: String (required)
  - `password`: String (required)
- **Response**:
  - **201 Created**: 
    - `message`: String
  - **400 Bad Request**: 
    - `message`: String

---

## Rides

### Get Rides
- **Endpoint**: `/api/v1/rides`
- **Method**: GET
- **Response**:
  - **200 OK**:
    - `rides`: Array of ride objects

### Create Ride
- **Endpoint**: `/api/v1/rides`
- **Method**: POST
- **Request Body**:
  - `pickup_location`: String (required)
  - `dropoff_location`: String (required)
  - `user_id`: String (required)
- **Response**:
  - **201 Created**:
    - `ride`: Ride object

---

## Ratings

### Submit Rating
- **Endpoint**: `/api/v1/ratings`
- **Method**: POST
- **Request Body**:
  - `ride_id`: String (required)
  - `rating`: Integer (1-5, required)
  - `comment`: String (optional)
- **Response**:
  - **201 Created**:
    - `message`: String
  - **400 Bad Request**:
    - `message`: String

### Get Ratings
- **Endpoint**: `/api/v1/ratings/{ride_id}`
- **Method**: GET
- **Response**:
  - **200 OK**:
    - `ratings`: Array of rating objects
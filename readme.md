# Restful-booker Collection

This project contains a Postman collection that interacts with the [Restful-booker API](https://restful-booker.herokuapp.com/), a simple API that simulates basic CRUD operations for bookings. The collection covers various endpoints, from creating an authentication token to deleting a booking, while running automated test scripts that check the status code, response data, and response times.

## Collection coverage

The collection includes the following request groups:

- **API health check:** Verifies that the API is available through `GET /ping`.
- **Authentication:** Creates an authentication token through `POST /auth`.
- **Create:** Creates a valid booking and tests a booking request with a missing value.
- **Read:** Retrieves a specific booking, lists all booking IDs, and searches for a booking by name.
- **Update:** Tests full updates with `PUT`, partial updates with `PATCH`, nonexistent booking IDs, and invalid authentication tokens.
- **Delete:** Tests deleting nonexistent bookings, deleting with an invalid token, successfully deleting a booking, and retrieving a previously deleted booking.

The test scripts validate HTTP status codes, response times below 3000 ms, response content, and JSON schema compliance where applicable.

## Getting started

1. Import this collection to Postman.
2. In Postman settings, allow scripts to modify your vault directly. This is required to store the username, password, and token in the vault.
3. The requests are already arranged for end-to-end testing. Use the Collection Runner to send requests to all endpoints while the test scripts validate the responses.

**Note:** There will be failed test cases in the collection, all of which relate to status codes (e.g., the API returns a 201 status code for a successful delete request when it should've been a 204).

## Collection variables

The collection includes the following predefined variables:

| Variable | Default value |
| --- | --- |
| `baseURL` | `https://restful-booker.herokuapp.com` |
| `incorrectToken` | `thisisanincorrecttoken` |
| `nonexistingID` | `123654` |

The collection also creates and updates `firstName`, `lastName`, `bookingID`, and `nonexistingID` during the test flow. The username, password, and authentication token are stored in Postman Vault rather than as collection variables.

# Request Anatomy

## Objective
To analyze the structure of HTTP requests including path parameters, query parameters, headers, and request body.

---

## Path Parameter

Example:
GET /posts/1

Observation:
- Returned a single JSON object.
- Resource identified directly by ID.
- Response structure: object.

Conclusion:
Path parameters are used to identify a specific resource.

---

## Query Parameter

Example:
GET /posts?id=1

Observation:
- Returned an array.
- Used for filtering.
- Even when filtering by ID, response format remains an array.

Conclusion:
Query parameters are typically used for filtering or searching resources.

---

## Header Analysis

Tested POST request with and without Content-Type header.

Observation:
- With correct header → processed normally.
- (Document actual behavior you observe.)

Conclusion:
Headers provide metadata that instruct the server how to interpret request data.

---

## Request Body

Used in POST request:
{
  "title": "day2",
  "body": "testing anatomy",
  "userId": 1
}

Observation:
- Body transmitted structured JSON data.
- Server returned created object.

Conclusion:
Request body carries structured data for resource creation or update.

---

## Key Differences Identified

- Path parameters identify a specific resource.
- Query parameters filter resources.
- Headers define request metadata.
- Body contains structured payload.

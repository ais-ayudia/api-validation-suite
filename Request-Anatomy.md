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

## Behavior When Resource Is Not Found

Test Case 1:
GET /posts/9999

Observation:
- Returned status 404 Not Found.

Test Case 2:
GET /posts?id=9999

Observation:
- Returned status 200 OK.
- Response body: [] (empty array).

Conclusion:
Path parameters return 404 when the resource does not exist.
Query parameters return an empty array when no matching results are found.

QA Implication:
Incorrect handling of these cases may cause frontend errors or misleading success responses.

---

## Header Analysis

Test Scenario:
POST request sent without Content-Type header.

Observation:
- Server still processed the request successfully.
- No 415 error was returned.

Conclusion:
The API is permissive regarding Content-Type validation.
In stricter production systems, incorrect Content-Type may result in 415 Unsupported Media Type.

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

## Response Structure Difference

Path Parameter Response:
- JSON object

Query Parameter Response:
- JSON array

Risk Consideration:
If frontend expects an object but receives an array (or vice versa), it may cause runtime errors or incorrect data rendering.

---

## Key Differences Identified

- Path parameters identify a specific resource.
- Query parameters filter resources.
- Headers define request metadata.
- Body contains structured payload.

---

## QA Relevance

Understanding request anatomy is critical for:

- Detecting inconsistent API behavior.
- Identifying incorrect response structures.
- Validating error handling logic.
- Preventing frontend integration issues.
- Ensuring contract stability between client and server.

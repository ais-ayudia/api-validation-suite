# API Testing Roadmap (14-Day Execution Plan)

This roadmap outlines a structured 14-day progression from HTTP fundamentals to semi-automation and professional test documentation.

---

## WEEK 1 — Core Foundation (Manual → Structured Testing)

### Day 1 — HTTP Deep Understanding
- Understand HTTP methods: GET, POST, PUT, DELETE
- Learn idempotent vs non-idempotent methods
- Analyze status code families (2xx, 4xx, 5xx)
- Execute at least 5 different requests
- Document behavioral differences and observations

---

### Day 2 — Request Anatomy
- Study request headers
- Work with JSON request body
- Compare query parameters vs path parameters
- Example comparison:
  - `/posts/1`
  - `/posts?id=1`
- Document functional differences and use cases

---

### Day 3 — Environment & Variable Strategy
- Create `{{base_url}}`
- Create `{{user_id}}`
- Refactor all requests to remove hardcoded values
- Document why hardcoded values create technical debt

---

### Day 4 — Assertion Basics
- Implement status code validation
- Validate JSON fields in response
- Add response time check
- Document the concept of deterministic testing

---

### Day 5 — Negative Testing
- Test invalid ID scenarios
- Test incorrect HTTP methods
- Test invalid request body
- Analyze API error consistency

---

### Day 6 — Edge Case Exploration
- Test empty values
- Test unexpected data types
- Test extreme values (large numbers, long strings)
- Document system behavior under edge inputs

---

### Day 7 — Test Case Documentation & Collection Structuring
- Create structured test case documentation:
  | ID | Scenario | Expected Result | Actual Result |
- Organize collection into:
  - Positive
  - Negative
  - Edge
- Export collection and store in repository

---

## WEEK 2 — Semi-Automation & Engineering Mindset

### Day 8 — Advanced Assertions
- Validate array length
- Validate specific field values
- Implement chained requests (store response → reuse variable)
- Document logic and purpose of each assertion

---

### Day 9 — Data-Driven Testing
- Use Collection Runner with JSON/CSV data
- Simulate multiple input values (e.g., multiple user IDs)
- Document why data-driven testing improves coverage

---

### Day 10 — Authentication Concepts
- Simulate Bearer token usage
- Implement header-based authorization
- Document authentication flow basics

---

### Day 11 — Error Handling Strategy
- Define characteristics of a good error response
- Analyze API consistency in error structure
- Document improvement recommendations

---

### Day 12 — Test Strategy Documentation
Create `TEST_STRATEGY.md` including:
- Scope
- Assumptions
- Risks
- Limitations
- Validation approach

---

### Day 13 — CI Introduction (Optional Advanced)
- Introduce Newman CLI execution
- Execute collection via command line
- (Optional) Conceptual integration with CI pipeline
- Document execution process and findings

---

### Day 14 — Final Refinement
- Clean repository structure
- Review and refactor documentation
- Ensure commit messages are meaningful
- Add final learning summary
- Export final version of collection

---

## Final Outcome

By the end of this roadmap, the repository should demonstrate:

- Structured API testing workflow
- Positive, negative, and edge case coverage
- Response validation via assertions
- Organized test documentation
- Semi-automation capability
- Professional QA documentation standards

# Postman API Testing Suite — Auth & Task CRUD Validation
REST API test collection in Postman covering auth, CRUD, negative, and invalid-ID checks

## Tools & APIs Used
- **Tool:** Postman (REST Client & Post-Response JavaScript Assertions)
- **APIs Tested:**
  - DummyJSON (`https://dummyjson.com`) — Authentication endpoints
  - JSONPlaceholder (`https://jsonplaceholder.typicode.com`) — Task/Post CRUD endpoints

## Test Scenarios Covered

| # | Request Name | Method & Endpoint | Scenario Type | Expected Status | Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Auth - Valid Login | `POST /auth/login` | Positive | `200 OK` | Passed |
| 2 | Auth - Invalid Password Login | `POST /auth/login` | Negative | `400 Bad Request` | Passed |
| 3 | Tasks - Get All Tasks | `GET /posts` | Positive | `200 OK` | Passed |
| 4 | Tasks - Get Single Task by ID | `GET /posts/1` | Positive | `200 OK` | Passed |
| 5 | Tasks - Get Non-Existent Task | `GET /posts/999999` | Negative / Boundary | `404 Not Found` | Passed |
| 6 | Tasks - Add New Task | `POST /posts` | Positive | `201 Created` | Passed |
| 7 | Tasks - Update Entire Task | `PUT /posts/1` | Positive (Full Update) | `200 OK` | Passed |
| 8 | Tasks - Partially Update Task Title | `PATCH /posts/1` | Positive (Partial Update) | `200 OK` | Passed |
| 9 | Tasks - Delete Task | `DELETE /posts/1` | Positive | `200 OK` | Passed |

## Post-Response Assertions
- Verified expected HTTP status codes (`200`, `201`, `400`, `404`).
- Verified API response latency stays under `1500ms`.
- Validated JSON structure and echoed payload fields (`title`, `id`, `accessToken`).

## How to Run
1. Download `Task-App-API-Collection.json` from this repository.
2. Open **Postman** → click **Import** → select the `.json` file.
3. Run individual requests or use **Collection Runner** to execute the full suite.

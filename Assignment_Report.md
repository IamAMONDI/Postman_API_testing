# API Testing with Postman - Assignment Report

**Student Name:** [Your Name]
**Student ID:** [Your ID]

## 1. API Choice and Base URL
- **API Choice:** GitHub API (Gists)
- **Base URL:** `https://api.github.com`
- **Reason for Choice:** The GitHub API is a standard, robust public API that provides full CRUD operations through Gists, and uses a realistic authentication method (Personal Access Token).

## 2. Authentication Method Used
The GitHub API uses **Personal Access Tokens (PAT)** which act similarly to an API Key or Bearer Token. I configured Postman to use **Bearer Token** authentication at the Collection level, which automatically applies the token to all requests. The token itself is stored securely in the Postman Environment as `{{access_token}}`.

*(Note: Unlike some APIs that use an endpoint like `/login` to generate a short-lived token, GitHub PATs are static and generated via the GitHub Web UI. Therefore, an authentication request to retrieve a token wasn't necessary, but a request to `/user` was used to verify the token's validity.)*

## 3. CRUD Operations

### Create (POST)
- **Endpoint:** `POST /gists`
- **Purpose:** Creates a new secret Gist.
- **Pre-request Script:** Used to generate a dynamic variable (`current_timestamp`) to append to the gist description.
- **Test Script:** Asserts a `201 Created` status code and dynamically extracts the `id` from the response to save it as the `gist_id` environment variable for subsequent requests.

**[INSERT POSTMAN SCREENSHOT HERE - Request & Response]**

### Read (GET)
- **Endpoint:** `GET /gists/{{gist_id}}`
- **Purpose:** Retrieves the specific Gist created in the previous step.
- **Test Script:** Asserts a `200 OK` status and verifies that the returned ID matches the `gist_id` environment variable.

**[INSERT POSTMAN SCREENSHOT HERE - Request & Response]**

### Update (PUT/PATCH)
- **Endpoint:** `PATCH /gists/{{gist_id}}`
- **Purpose:** Updates the description and content of the existing Gist.
- **Test Script:** Asserts a `200 OK` status and checks that the description field was successfully updated.

**[INSERT POSTMAN SCREENSHOT HERE - Request & Response]**

### Delete (DELETE)
- **Endpoint:** `DELETE /gists/{{gist_id}}`
- **Purpose:** Deletes the Gist to clean up resources.
- **Test Script:** Asserts a `204 No Content` status code indicating successful deletion.

**[INSERT POSTMAN SCREENSHOT HERE - Request & Response]**


## 4. Environment Variables and Automation
Environment variables were heavily utilized to make the collection dynamic and automated:
- `base_url`: Avoids repeating `https://api.github.com` across all requests.
- `access_token`: Stores the authentication token securely.
- `gist_id`: Automatically populated by the POST request's test script and used by the GET, PATCH, and DELETE requests.
- `current_timestamp`: Automatically populated by a pre-request script in the POST request.

This allowed the entire collection to be run sequentially in the **Collection Runner** without any manual intervention.

## 5. Collection Runner Execution
The entire suite was executed in the Collection Runner, running all 5 requests in order and validating all automated tests.

**[INSERT COLLECTION RUNNER SCREENSHOT HERE - Showing all successful tests]**

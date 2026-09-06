# GitHub API Postman Assignment

This directory contains everything you need to complete your Postman API Assignment using the GitHub API.

## Files Included:
1. `GitHub_Gists_API.postman_collection.json` - The Postman Collection containing all requests, tests, and scripts.
2. `GitHub_API_Environment.postman_environment.json` - The environment setup with necessary variables.
3. `Assignment_Report.md` (in your artifacts) - The template for your final submission report.

## Step-by-Step Instructions:

### Step 1: Generate a GitHub Personal Access Token
1. Go to your GitHub account settings -> **Developer settings** -> **Personal access tokens** -> **Tokens (classic)**.
2. Click **Generate new token (classic)**.
3. Give it a note (e.g., "Postman Assignment").
4. Select the **gist** scope (this is required to create and delete gists).
5. Generate the token and **copy it immediately** (you won't be able to see it again).

### Step 2: Import into Postman
1. Open Postman.
2. Click **Import** and select both the `.postman_collection.json` and `.postman_environment.json` files from this directory.
3. In the top right corner of Postman, select the **GitHub API Environment** from the environment dropdown.
4. Click the "eye" icon next to the environment dropdown, click **Edit**, and paste your GitHub token into the `Current Value` field for `access_token`. Save it.

### Step 3: Run the Requests and Take Screenshots
1. Open the **GitHub Gists API** collection.
2. Run each request one by one (Verify Authentication, POST, GET, PATCH, DELETE).
3. Take screenshots of the Request and Response for each and insert them into your `Assignment_Report.md`.

### Step 4: Collection Runner
1. Click the three dots `...` next to the collection name and select **Run collection**.
2. Run the collection.
3. Take a screenshot of the successful test results for your report.

### Step 5: Submit
Upload your Collection, Environment, and the completed Report to your GitHub repository and submit the link!

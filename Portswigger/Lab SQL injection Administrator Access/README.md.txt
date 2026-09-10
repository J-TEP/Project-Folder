Overview
Targeting the product category filter parameter (GET /filter?category=Gifts) via the Burp Suite Repeater to execute a UNION-based SQL injection attack. By appending a two-column payload ('%20UNION%20SELECT%20username,%20password%20from%20users--), the query extracts credentials directly from the backend database's users table, returning a 200 OK response that prints the administrator credentials in the body for account access.

Step-by-Step Implementation

Step 1: Intercept the Category Request
Capture the product category request using the Burp Suite proxy after clicking a filter link:
GET /filter?category=Gifts HTTP/1.1

Step 2: Forward to Repeater
Send the captured request from the proxy history into the Repeater tool to manually modify and test payloads.

Step 3: Inject the Credential Extraction Payload
Append the SQL injection string to the category parameter to query the users table for both the username and password columns:
GET /filter?category=Gifts'%20UNION%20SELECT%20username,%20password%20from%20users--

Step 4: Retrieve Administrator Credentials
Send the request to receive a 200 OK response, scroll down through the response body to locate the extracted administrator username and password, and use those credentials to log into the application.
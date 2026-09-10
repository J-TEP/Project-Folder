Overview
Grabbing the Gifts category request through the Burp Suite proxy (GET /filter?category=Gifts) and sending it to the Repeater to test UNION injection payloads. By appending a single quote and rotating the target string ('OphMU') through incremental NULL parameters ('%20UNION%20SELECT%20null,'OphMU',null--), you test each column position.

Step-by-Step Implementation

Step 1: Intercept the Request
Capture the category filter request using the Burp Suite proxy:
GET /filter?category=Gifts HTTP/1.1

Step 2: Send to Repeater
Send the captured request from the proxy history into the Repeater tool to manually modify and test payloads.

Step 3: Test Column Positions
Append the payload to the category parameter, modifying it to go through each column position until it accepts the syntax:
GET /filter?category=Gifts%20UNION%20SELECT%20null,'OphMU',null--

Step 4: Monitor Responses
Watch for HTTP status codes during testing. A 500 Internal Server Error means the server is rejecting the column/data type placement, while a 200 OK response indicates a successful match that renders the exact target string you are looking for.
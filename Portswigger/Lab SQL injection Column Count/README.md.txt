Overview & Objective: Exploit a SQL injection vulnerability using a UNION attack to determine the exact number of columns returned by the application's original database query.

Step 1: Navigate to the target web application and click on the "Gifts" category filter to generate the initial baseline request (GET /filter?category=Gifts).

Step 2: Capture that request in Burp Suite Proxy and send it to Burp Repeater.

Step 3: Modify the category parameter value by appending the SQL injection payload starting with a single quote to close the string literal, followed by the union syntax and a test number of null placeholders: Gifts'%20UNION%20SELECT%20NULL,NULL,NULL--.

Step 4: Send the modified request in Repeater, adjusting the number of NULL values up or down until the application responds with a 200 OK status instead of a database error, confirming the correct column count and completing the lab.
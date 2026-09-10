Overview & Objective: Bypass the application's authentication mechanism via SQL injection by injecting a payload into the username field of the login form, forcing the backend database to evaluate a true condition (1=1), ignore the password check, and issue an administrator session cookie.

Step 1: Navigate to the target login page, input a test username and password, and capture the resulting POST /login request in Burp Suite Proxy.

Step 2: Right-click the captured request and send it to Burp Repeater.

Step 3: Modify the username parameter in the request body to inject the SQL payload: administrator'%20OR%201=1-- while leaving a placeholder value in the password field.

Step 4: Send the modified request in Repeater and observe the 302 Found response header containing the new administrative Set-Cookie session value.

Step 5: Copy the generated session cookie value from the 302 response and update your browser's active session cookie, or use Burp's browser to follow the redirection path to the administrator account page.

Step 6: Verify success by confirming the HTTP 200 OK response or checking the browser interface to ensure the lab completion banner appears, proving full administrator access was achieved.
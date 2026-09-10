Overview & Objective: Launch the lab, access the target web application, and click on the "Gifts" category to generate an HTTP request routed through the Burp Suite proxy. The objective is to inject a logical SQL condition into the database query to bypass filtering and retrieve unreleased items.

Step 1: Capture the baseline request in Burp Proxy, which appears as GET /filter?category=Gifts.

Step 2: Right-click the request and send it to Burp Repeater.

Step 3: Modify the category parameter value in the request line by appending the SQL injection payload: Gifts'%20OR%201=1--. The single quote (') closes the SQL string literal, %20OR%201=1 forces a true condition, and -- comments out the rest of the query.
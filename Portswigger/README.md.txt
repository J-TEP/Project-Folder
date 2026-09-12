# PortSwigger Web Security Academy - Practical Labs

## Project Overview
This repository contains technical documentation, request/response analysis, and hands-on walkthroughs demonstrating core web application vulnerabilities solved through the PortSwigger Web Security Academy.

## Topics Covered
* **SQL Injection: Retrieving Hidden Data** — Manipulating query logic to bypass application filters and display unconstrained database records.
  * *Methodology*: Injecting Boolean conditions (such as `' OR 1=1--`) into vulnerable input parameters (like product categories) to alter the WHERE clause evaluation, forcing the database to return all records regardless of constraints.
* **SQL Injection: Determining Column Count** — Utilizing `ORDER BY` clauses to map database table structures for UNION-based attacks.
  * *Methodology*: Sequentially appending `ORDER BY 1`, `ORDER BY 2`, etc., to the injection point until an error or different response occurs, confirming the exact number of columns expected by the original SQL query.
* **SQL Injection: Identifying Text Columns** — Executing targeted injection strings to verify string-compatible data columns in query responses.
  * *Methodology*: Using `UNION SELECT NULL, 'a', NULL--` statements to systematically test each column position in the query response structure, ensuring that injected data types align with the database columns before extracting data.
* **SQL Injection: Login Bypass** — Exploiting authentication parameters to compromise login logic and access restricted accounts.
  * *Methodology*: Injecting syntax characters like `'` combined with logical operators (`OR '1'='1`) into username fields to evaluate authentication checks to true, bypassing password verification entirely.
* **SQL Injection: Administrator Access** — Leveraging union and logical operators to extract administrative credentials and elevate privileges.
  * *Methodology*: Crafting custom `UNION SELECT` payloads combined with database metadata lookups to query user tables, retrieve administrator usernames and password hashes, and access high-privilege dashboards.
* **API Security: Unused Endpoint Exploitation** — Discovering and interacting with undocumented API routes to bypass standard access controls.
  * *Methodology*: Performing comprehensive content discovery using Burp Suite's site map and target history to unearth hidden or deprecated API endpoints that lack proper authentication enforcement, allowing direct resource manipulation.
* **API Security: Exploiting Server-Side Parameter Pollution in a Query String** — Injecting query syntax characters to manipulate backend API request structures.
  * *Methodology*: Interacting with features like password reset and injecting query syntax characters like `&` (`%26`) and `#` (`%23`) to trick the backend API into processing hidden parameters, leaking an administrative password reset token, and ultimately deleting the user `carlos` to complete the lab.

## Tools & Methodology
* **Burp Suite:** Used as the primary intercepting proxy to capture, map, and analyze HTTP traffic.
* **Burp Repeater:** Utilized for manual request modification, payload injection tuning, and observing application responses.
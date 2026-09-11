# PortSwigger Web Security Academy - Practical Labs

## Project Overview
This repository contains technical documentation, request/response analysis, and hands-on walkthroughs demonstrating core web application vulnerabilities solved through the PortSwigger Web Security Academy.

## Topics Covered
* **SQL Injection: Retrieving Hidden Data** — Manipulating query logic to bypass application filters and display unconstrained database records.
* **SQL Injection: Determining Column Count** — Utilizing `ORDER BY` clauses to map database table structures for UNION-based attacks.
* **SQL Injection: Identifying Text Columns** — Executing targeted injection strings to verify string-compatible data columns in query responses.
* **SQL Injection: Login Bypass** — Exploiting authentication parameters to compromise login logic and access restricted accounts.
* **SQL Injection: Administrator Access** — Leveraging union and logical operators to extract administrative credentials and elevate privileges.
* **API Security: Unused Endpoint Exploitation** — Discovering and interacting with undocumented API routes to bypass standard access controls.

## Tools & Methodology
* **Burp Suite:** Used as the primary intercepting proxy to capture, map, and analyze HTTP traffic.
* **Burp Repeater:** Utilized for manual request modification, payload injection tuning, and observing application responses.
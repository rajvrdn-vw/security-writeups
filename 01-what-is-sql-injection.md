# Write-up #1: What is SQL Injection?

## Summary
SQL Injection is a vulnerability where an attacker can inject
malicious SQL commands into a web application's database query
through user input fields.

## How It Works
When a web application takes user input (like a login form) and
directly places it into a SQL query without sanitizing it, an
attacker can manipulate the query logic.

Example: Typing `' OR 1=1 --` in a username field can bypass
authentication because `1=1` always evaluates to true.

## Impact
- Unauthorized access to any account
- Reading/modifying/deleting the entire database
- In some cases, full server compromise

## How to Prevent It
- Use parameterized queries / prepared statements
- Use ORM frameworks (like Django's ORM) which handle this
  automatically
- Never concatenate raw user input into SQL strings
- Validate and sanitize all user inputs

## What I Learned
SQL Injection exists because developers trust user input. The
lesson: never trust anything that comes from the user side.

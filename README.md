# Express.js Unhandled Error: Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  lack of error handling for invalid input.  The `bug.js` file shows a route that is vulnerable to errors when an invalid user ID is provided. The `bugSolution.js` file provides a corrected version with proper error handling.

## Bug Description
The original code attempts to parse a user ID from the request parameters and uses `parseInt()` without checking if the parameter is actually a number. If a non-numeric ID is provided, `parseInt()` will return `NaN`, and the subsequent `find()` operation will fail silently or throw an exception, leading to an unexpected error or app crash.

## Solution
The solution involves adding input validation to check if the user ID is a number before attempting to parse it.  If the ID is invalid, an appropriate error response (e.g., 400 Bad Request) is returned.
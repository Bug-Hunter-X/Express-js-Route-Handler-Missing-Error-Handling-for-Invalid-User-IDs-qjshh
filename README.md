# Express.js Route Handler Bug: Missing Error Handling

This repository demonstrates a common bug in Express.js route handlers: missing error handling for invalid input.  The example focuses on a route that retrieves a user by ID.  The original code fails to handle cases where the provided user ID is not a valid integer, leading to potential crashes or unexpected behavior.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides a corrected version with robust error handling.

## Bug Description

The route handler attempts to parse the user ID from the request parameters as an integer using `parseInt()`. However, it doesn't check if the result of `parseInt()` is actually a valid integer (NaN) or handle the case where no user with that ID exists.  This can result in runtime errors or unexpected responses.

## Solution

The corrected code in `bugSolution.js` adds comprehensive error handling.  It checks if `parseInt(userId)` resulted in NaN and handles the case gracefully by returning a 400 Bad Request error.  It also explicitly checks if the user exists before sending the response.
# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the provided code handles requests to `/users/:id` but fails to gracefully handle cases where `:id` is not a valid integer.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides a corrected version.

## Bug

The original code attempts to parse the user ID as an integer using `parseInt()` without any validation. If the `:id` parameter is not an integer (e.g., a string, or null), this will lead to an error, potentially crashing the server or returning an unexpected response.

## Solution

The solution adds error handling to check if the `userId` is a valid integer before attempting to find the user.  If it's not an integer, it sends a 400 Bad Request response; otherwise, it proceeds with the existing logic.
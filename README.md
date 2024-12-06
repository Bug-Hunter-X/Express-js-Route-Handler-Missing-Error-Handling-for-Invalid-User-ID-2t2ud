# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  The example shows a route that fetches a user by ID.  If the ID is not a valid number, the application will crash or return unexpected results.

## Bug

The `bug.js` file contains the erroneous code.  The route handler attempts to parse the `userId` as an integer without checking if it's actually a number. If a non-numeric value is passed as a parameter, `parseInt()` will return `NaN`, causing the `users.find()` method to fail silently or throw an exception (depending on how the `users` array is implemented) leading to an error.

## Solution

The `bugSolution.js` file provides a corrected version of the code.  It includes checks to ensure the `userId` is a number before attempting to parse it and performs checks for the existence of the user in the array.
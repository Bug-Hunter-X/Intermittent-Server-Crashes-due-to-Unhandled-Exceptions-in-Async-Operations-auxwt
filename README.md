# Node.js Server Crash Bug

This repository demonstrates a common Node.js issue: intermittent server crashes caused by unhandled exceptions during asynchronous operations. The `server.js` file contains the buggy code, while `server-fixed.js` provides a solution.

## Bug Description

The Node.js server occasionally crashes without any clear error messages in the console. This is because asynchronous operations (like file uploads or database queries) might throw exceptions that are not properly caught, leading to process termination.

## Bug Reproduction

1. Clone this repository.
2. Navigate to the directory.
3. Run `node server.js`. 
4. Simulate a condition that triggers the error (e.g.  Try to access a non-existent file, or simulate a database error in case database operations are involved)

## Solution

The `server-fixed.js` file demonstrates how to properly handle exceptions in asynchronous code using `try...catch` blocks and `async/await` error handling.

This improved error handling ensures that exceptions don't bring down the entire server. Instead, errors are logged, and the server can continue to function gracefully. 

Always implement robust error handling in your asynchronous Node.js applications to prevent these kinds of crashes. 
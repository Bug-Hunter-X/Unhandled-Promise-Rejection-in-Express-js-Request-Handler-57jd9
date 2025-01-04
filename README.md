# Unhandled Promise Rejection in Express.js

This repository demonstrates a common error in Node.js Express.js applications: silently failing requests due to unhandled promise rejections within asynchronous request handlers. The server logs the error, but the client receives no indication of the problem.

## Bug

The `bug.js` file shows an Express.js server with a route that performs an asynchronous operation.  This operation has a 50% chance of rejecting with an error.  The error handling only logs the error to the console; it doesn't send an error response to the client. This leads to a poor user experience and makes debugging difficult.

## Solution

The `bugSolution.js` file demonstrates the correct way to handle promise rejections in Express.js.  It uses a `try...catch` block to handle the promise rejection and sends an appropriate error response to the client (HTTP 500 status code).

## How to Run

1. Clone this repository.
2. Navigate to the repository's directory.
3. Install dependencies: `npm install express`
4. Run the buggy server: `node bug.js`
5. Run the fixed server: `node bugSolution.js`
6. Test using curl or a browser to see the difference in error handling.
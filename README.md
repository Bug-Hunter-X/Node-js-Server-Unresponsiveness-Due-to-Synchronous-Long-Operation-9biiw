# Node.js Server Unresponsiveness
This repository demonstrates a common issue in Node.js where a server becomes unresponsive due to a long-running synchronous operation within the request handler.  The problem is that Node.js is single-threaded, and a blocking operation prevents it from handling other requests.

## Bug
The `server.js` file contains a simple HTTP server with a request handler that simulates a 5-second delay.  This blocks the event loop, causing the server to appear unresponsive during this time.

## Solution
The `server-solution.js` file demonstrates how to resolve the issue by using asynchronous operations.  Instead of a `while` loop, it uses `setTimeout` to schedule the response after the delay.
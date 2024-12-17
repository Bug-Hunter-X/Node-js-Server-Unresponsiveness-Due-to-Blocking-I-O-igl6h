# Node.js Server Unresponsiveness Due to Blocking I/O

This repository demonstrates a common issue in Node.js applications where a long-running synchronous operation in a request handler blocks the event loop, causing the server to become unresponsive.  The solution illustrates how to use asynchronous operations or worker threads to avoid blocking the event loop.

## Bug
The `server.js` file contains a simple HTTP server with a request handler that simulates a long-running task (5 seconds). This synchronous operation blocks the event loop, preventing the server from responding to other requests during this time. Attempting to access the server while the long-running task is active will result in a timeout.

## Solution
The `serverSolution.js` file demonstrates the solution by utilizing asynchronous operations to prevent the event loop from blocking.  This allows the server to remain responsive even during lengthy operations.
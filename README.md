# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler can cause the server to become unresponsive.  The provided `bug.js` file contains the problematic code, and `bugSolution.js` shows how to fix it by using asynchronous operations.

## Problem

The `bug.js` example uses a `while` loop to simulate a 5-second long operation.  This blocks the event loop, preventing the server from handling other requests.  Any client attempting to connect during this time will experience significant delays or timeouts.

## Solution

The `bugSolution.js` demonstrates the correct approach using asynchronous operations.  This prevents the blocking of the event loop and ensures the server remains responsive to multiple concurrent requests.

## How to reproduce

1. Clone this repository.
2. Run `node bug.js`.
3. Try to make multiple requests to `http://localhost:3000` while the server is running.  Observe the slow response times or timeouts.
4. Then run `node bugSolution.js`, and repeat the request process to see the improvement.
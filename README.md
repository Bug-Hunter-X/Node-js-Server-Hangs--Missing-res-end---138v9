# Node.js Server Hang: Missing res.end()

This repository demonstrates a common error in Node.js HTTP servers: forgetting to call `res.end()` to signal the end of the response.  This can lead to clients hanging indefinitely, waiting for a response that never arrives.

The `bug.js` file shows the problematic code. The `bugSolution.js` file provides the corrected version.

## How to Reproduce

1. Clone this repository.
2. Run `node bug.js`.
3. Try accessing `http://localhost:3000` in your browser or using a tool like `curl`. You'll observe a hang.
4. Run `node bugSolution.js`. Accessing `http://localhost:3000` will now return a successful response.

## Lesson Learned

Always remember to call `res.end()` after writing to the response in your Node.js HTTP server. This ensures that the client receives the complete response and the connection is properly closed.
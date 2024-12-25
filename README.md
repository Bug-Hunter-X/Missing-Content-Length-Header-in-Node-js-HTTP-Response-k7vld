# Missing Content-Length Header in Node.js HTTP Response

This repository demonstrates a common error in Node.js HTTP servers: failure to set the `Content-Length` header.  This can lead to issues with clients that rely on this header for proper response handling, potentially resulting in incomplete downloads or unexpected behavior.

The `bug.js` file shows the problematic code, and `bugSolution.js` provides the corrected version.

## How to reproduce

1. Clone this repository.
2. Run `node bug.js`.
3. Observe the behavior of clients connecting to the server.  Some clients might not handle the response correctly due to the missing `Content-Length` header.

## Solution

The solution involves explicitly setting the `Content-Length` header in the HTTP response.  This tells the client exactly how many bytes to expect, ensuring correct data transfer.
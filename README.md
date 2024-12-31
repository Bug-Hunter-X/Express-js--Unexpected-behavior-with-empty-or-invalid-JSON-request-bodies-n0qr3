# Express.js: Handling Empty and Invalid JSON Request Bodies

This repository demonstrates a common issue in Express.js applications where parsing JSON request bodies fails when the body is empty or contains invalid JSON data.  The application incorrectly handles these situations, potentially leading to unexpected behavior or errors.

## Bug Description

The `express.json()` middleware is used to parse JSON request bodies. However, when an empty request body or one with invalid JSON is sent, the `req.body` object will be undefined, causing issues with subsequent code that relies on the parsed data.  This leads to unexpected application behavior rather than a proper error response.

## Solution

The solution involves adding error handling to check if `req.body` is defined before processing it, and also adding validation to check if the request body is valid JSON.  If the request body is invalid, a more appropriate error response is returned to the client.
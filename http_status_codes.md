# HTTP Status Codes

## 1xx Informational

100 - Continue: Server received request headers; client should proceed to send the body.

101 - Switching Protocols: Server is switching protocols as requested (e.g. HTTP -> WebSocket).

## 2xx Success

200 - OK: Request succeeded. Server returned the requested data. Most common response.

201 - Created: A new resource was successfully created (e.g. after a sign-up or form submit).

204 - No Content: Request succeeded but no content to return. Common after a DELETE action.

206 - Partial Content: Server is returning only part of the resource (e.g. video streaming / resuming download).

## 3xx Redirection

301 - Moved Permanently: Page has moved to a new URL forever. Browsers and search engines update links automatically.

302 - Found (Temporary Redirect): Page is temporarily at a different URL. Used for maintenance or login redirects.

304 - Not Modified: Cached version is still valid. Browser uses its local copy - saves bandwidth.

307 - Temporary Redirect: Like 302 but the HTTP method (GET/POST) must stay the same. Safer for form submissions.

308 - Permanent Redirect: Like 301 but the HTTP method must stay the same.

## 4xx Client Errors

400 - Bad Request: Server couldn't understand the request due to invalid syntax (malformed URL or bad form data).

401 - Unauthorized: You need to log in. Server doesn't know who you are yet.

403 - Forbidden: Server knows who you are but you don't have permission to access this resource.

404 - Not Found: The most famous one! Page or resource doesn't exist - deleted or the link is wrong.

405 - Method Not Allowed: HTTP method used (e.g. POST) is not supported for this endpoint.

408 - Request Timeout: Server waited too long for the client to send a request and gave up.

409 - Conflict: Request conflicts with current state (e.g. creating a username that already exists).

410 - Gone: Like 404, but confirms the resource existed before and was intentionally removed.

413 - Payload Too Large: File or data you're uploading is bigger than the server allows.

414 - URI Too Long: The URL you sent is too long for the server to process.

415 - Unsupported Media Type: Server refuses to accept the file format you sent.

422 - Unprocessable Entity: Request was well-formed but had semantic errors (common in APIs with validation).

429 - Too Many Requests: You've sent too many requests in a short time. Server is rate-limiting you - slow down!

## 5xx Server Errors

500 - Internal Server Error: Something went wrong on the server's side. Not your fault - the website has a bug or crash.

501 - Not Implemented: Server doesn't support the feature needed to fulfill the request.

502 - Bad Gateway: Server acting as a gateway got an invalid response from an upstream server.

503 - Service Unavailable: Server is temporarily down - maintenance or overloaded with traffic.

504 - Gateway Timeout: Server didn't get a response in time from another server it was waiting on.

505 - HTTP Version Not Supported: Server doesn't support the HTTP version used in the request.

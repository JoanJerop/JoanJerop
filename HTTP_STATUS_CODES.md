**HTTP Status Codes Documentation**

**Overview**
HTTP status codes are three-digit numbers returned by web servers to indicate the result of a client's request. 
They play a key role in web development, API integration, and troubleshooting.

**Status Code Categories**

1xx - Informational Responses
These codes indicate that the request was received and is being processed.

| Code | Status | Description |
|------|--------|-------------|
| 100 | Continue | The server has received the request headers and the client should proceed to send the request body |
| 101 | Switching Protocols | The server is switching protocols as requested by the client |
| 102 | Processing | The server has received and is processing the request, but no response is available yet |

2xx - Success
These codes indicate that the request was successfully received, understood, and accepted.

| Code | Status | Description |
|------|--------|-------------|
| 200 | OK | The request was successful |
| 201 | Created | The request was successful and a new resource was created |
| 202 | Accepted | The request has been accepted for processing, but processing is not complete |
| 204 | No Content | The server successfully processed the request but is not returning any content |
| 206 | Partial Content | The server is delivering only part of the resource due to a range header |

3xx - Redirection
These codes indicate that further action needs to be taken to complete the request.

| Code | Status | Description |
|------|--------|-------------|
| 300 | Multiple Choices | Multiple options for the resource that the client may follow |
| 301 | Moved Permanently | The resource has been permanently moved to a new URL |
| 302 | Found | The resource temporarily resides under a different URL |
| 304 | Not Modified | The resource has not been modified since the last request |
| 307 | Temporary Redirect | The request should be repeated with another URL, but future requests should still use the original URL |
| 308 | Permanent Redirect | The request and all future requests should be repeated using another URL |

4xx - Client Errors
These codes indicate that the request contains bad syntax or cannot be fulfilled by the server.

| Code | Status | Description |
|------|--------|-------------|
| 400 | Bad Request | The server cannot process the request due to client error |
| 401 | Unauthorized | Authentication is required and has failed or has not been provided |
| 403 | Forbidden | The server understood the request but refuses to authorize it |
| 404 | Not Found | The requested resource could not be found |
| 405 | Method Not Allowed | The request method is not supported for the requested resource |
| 408 | Request Timeout | The server timed out waiting for the request |
| 409 | Conflict | The request could not be completed due to a conflict with the current state |
| 410 | Gone | The requested resource is no longer available and will not be available again |
| 413 | Payload Too Large | The request entity is larger than limits defined by server |
| 415 | Unsupported Media Type | The media format of the requested data is not supported |
| 422 | Unprocessable Entity | The request was well-formed but contains semantic errors |
| 429 | Too Many Requests | The user has sent too many requests in a given amount of time |

5xx - Server Errors
These codes indicate that the server failed to fulfill a valid request.

| Code | Status | Description |
|------|--------|-------------|
| 500 | Internal Server Error | A generic error message when the server encounters an unexpected condition |
| 501 | Not Implemented | The server either does not recognize the request method or lacks the ability to fulfill it |
| 502 | Bad Gateway | The server received an invalid response from an inbound server |
| 503 | Service Unavailable | The server is currently unavailable (overloaded or down for maintenance) |
| 504 | Gateway Timeout | The server did not receive a timely response from an upstream server |
| 505 | HTTP Version Not Supported | The server does not support the HTTP protocol version used in the request |

Common Use Cases

Web Development
- **200 OK**: Successful page load or API response
- **404 Not Found**: Broken links or missing pages
- **500 Internal Server Error**: Server-side code issues

API Development
- **201 Created**: Successfully created a new resource (POST requests)
- **400 Bad Request**: Invalid request parameters
- **401 Unauthorized**: Missing or invalid authentication
- **403 Forbidden**: Valid authentication but insufficient permissions

SEO and Website Management
- **301 Moved Permanently**: Redirect old URLs to new ones
- **404 Not Found**: Monitor and fix broken links
- **503 Service Unavailable**: Maintenance mode pages

**Testing HTTP Status Codes**

**Using cURL**
```bash
# Check status code of a website
curl -I https://example.com

# Get detailed response including status code
curl -v https://example.com
```

**Using Browser Developer Tools**
1. Open Developer Tools (F12)
2. Go to Network tab
3. Reload the page
4. Check the Status column for each request

**Online Tools**
- HTTPStatus.io
- HTTP Status Code Checker tools
- Postman for API testing

**Best Practices**

**For Developers**
1. **Use appropriate status codes** - Don't return 200 OK for error conditions
2. **Provide meaningful error messages** - Include helpful information in response bodies
3. **Handle redirects properly** - Use 301 for permanent redirects, 302 for temporary
4. **Implement proper error handling** - Catch and return appropriate 5xx codes

**For Website Owners**
1. **Monitor 404 errors** - Set up tracking for broken links
2. **Implement custom error pages** - Provide helpful 404 and 500 error pages
3. **Use redirects wisely** - Implement 301 redirects for URL changes
4. **Set up monitoring** - Track 5xx errors to identify server issues

**Quick Reference Cheat Sheet**

**Most Common Codes to Remember:**
- **200** - Success
- **301** - Permanent redirect
- **400** - Bad request
- **401** - Unauthorized
- **403** - Forbidden
- **404** - Not found
- **500** - Server error
- **503** - Service unavailable

**Supporting Links**
- [Mozilla MDN HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
- [RFC 7231 - HTTP/1.1 Semantics](https://tools.ietf.org/html/rfc7231)
- [HTTP Status Dogs](https://httpstatusdogs.com/)

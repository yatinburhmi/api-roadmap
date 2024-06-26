### HTTP

## What is HTTP?

HTTP is a protocol for fetching resources such as HTML documents.

![alt text](https://mdn.github.io/shared-assets/images/diagrams/http/overview/http-layers.svg)

**Requests** consist of the following elements:

An **HTTP method**, usually a verb like GET, POST, or a noun like OPTIONS or HEAD that defines the operation the client wants to perform. Typically, a client wants to fetch a resource (using GET) or post the value of an HTML form (using POST), though more operations may be needed in other cases.
The **path of the resource to fetch**; the URL of the resource stripped from elements that are obvious from the context, for example without the protocol (http://), the domain (here, developer.mozilla.org), or the TCP port (here, 80).
The **version of the HTTP protocol**.
**Optional headers** that convey additional information for the servers.
**A bod**y, for some methods like POST, similar to those in responses, which contain the resource sent.

**Responses** consist of the following elements:

The version of the HTTP protocol they follow.
A **status code**, indicating if the request was successful or not, and why.
A **status message**, a non-authoritative short description of the status code.
**HTTP headers**, like those for requests.
Optionally, a **body** containing the fetched resource.

## HTTP Request Methods

HTTP defines a set of request methods to indicate the desired action to be performed for a given resource. These request methods are sometimes referred to as HTTP verbs.

GET
The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.

POST
The POST method submits an entity to the specified resource, often causing a change in state or side effects on the server.

PUT
The PUT method replaces all current representations of the target resource with the request payload.

PATCH
The PATCH method applies partial modifications to a resource.

DELETE
The DELETE method deletes the specified resource.

HEAD
The HEAD method asks for a response identical to a GET request, but without the response body.

## HTTP Status Codes

1xx Informational

2xx Success - This class of status codes indicates the action requested by the client was received, understood, accepted, and processed successfully.

200 OK
General status code. Most common code used to indicate success.

The request has succeeded. The information returned with the response is dependent on the method used in the request, for example:

GET an entity corresponding to the requested resource is sent in the response.
HEAD the entity-header fields corresponding to the requested resource are sent in the response without any message-body.
POST an entity describing or containing the result of the action,
TRACE an entity containing the request message as received by the end server.

3xx Redirection
This class of status code indicates that further action needs to be taken by the client in order to fulfill the request.

★ 304 Not Modified
Indicates the resource has not been modified since last requested.

4xx Client Error
The 4xx class of status code is intended for cases in which the client seems to have erred.

★ 400 Bad Request
General error when fulfilling the request would cause an invalid state. Syntax and domain validation errors, missing data, etc. are some examples.

★ 401 Unauthorized
Error code response for missing or invalid authentication token.

★ 403 Forbidden
Error code for user not authorized to perform the operation or the resource is unavailable for some reason (e.g. time constraints, etc.).

★ 404 Not Found
Used when the requested resource is not found, whether it doesn’t exist or if there was a 401 or 403 that, for security reasons, the service wants to mask.

★ 409 Conflict
Indicates that the request could not be processed because of conflict in the request, such as an edit conflict.

5xx Server Error
The server failed to fulfill an apparently valid request.

★ 500 Internal Server Error
The general catch-all error when the server-side throws an exception. This indicates a service outage

502 Bad Gateway
The server, while acting as a gateway or proxy, received an invalid response from the upstream server it accessed in attempting to fulfill the request.

503 Service Unavailable
The server is currently unavailable (because it is overloaded or down for maintenance). Generally, this is a temporary state.

504 Gateway Timeout
The server was acting as a gateway or proxy and did not receive a timely response from the upstream server specified by the URI

## HTTP Headers

The HTTP headers are used to pass additional information between the clients and the server through the request and response header. All the headers are case-insensitive, headers fields are separated by colon, key-value pairs in clear-text string format.

There are four kinds of headers context-wise:

General Header: This type of headers applied on Request and Response headers both but with out affecting the database body.
Request Header: This type of headers contains information about the fetched request by the client.
Response Header: This type of headers contains the location of the source that has been requested by the client.
Entity Header: This type of headers contains the information about the body of the resources like MIME type, Content-length.

[Read More](https://www.geeksforgeeks.org/http-headers/)

## HTTP Cookies

HTTP protocol is stateless by default - that means it is going to constantly forget what the user has done on the site unless we have a way to remember that.  
A cookie (also known as a web cookie or browser cookie) is a small piece of data a server sends to a user's web browser. The browser may store cookies, create new cookies, modify existing ones, and send them back to the same server with later requests. **Cookies enable web applications to store limited amounts of data and remember state information; by default the HTTP protocol is stateless.**
Once the cookies are set by the server in the client(browser), the subsequent requests made by the client to the same server(same domain) will include those cookies in the request headers.

**What cookies are used for**
Typically, the server will use the contents of HTTP cookies to determine whether different requests come from the same browser/user and then issue a personalized or generic response as appropriate.

**Cookies are mainly used for three purposes:**

**Session management:** User sign-in status, shopping cart contents, game scores, or any other user session-related details that the server needs to remember.
**Personalization:** User preferences such as display language and UI theme.
**Tracking:** Recording and analyzing user behavior.

[Read More](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)

## CORS - Cross-Origin Resource Sharing

## HTTP Caching

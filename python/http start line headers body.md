https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages

HTTP requests, and responses, share similar structure and are composed of:

A start-line describing the requests to be implemented, or its status of whether successful or a failure. This start-line is always a single line.
An optional set of HTTP headers specifying the request, or describing the body included in the message.
A blank line indicating all meta-information for the request has been sent.
An optional body containing data associated with the request (like content of an HTML form), or the document associated with a response. The presence of the body and its size is specified by the start-line and HTTP headers.

The start-line and HTTP headers of the HTTP message are collectively known as the head of the requests, whereas its payload is known as the body.

![image](https://user-images.githubusercontent.com/85205970/167057986-3291ec69-0aec-4093-ae8e-cf3e81b3e54f.png)

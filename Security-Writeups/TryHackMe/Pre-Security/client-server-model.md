# Client-Server Model

- Basics of how computers talk to each other over a network.

## Service, Client and Server

- **Service**: The thing being offered that you're trying to use (like a website).
- **Client**: The program making the request for the service, like a web browser (but it can be any program that sends requests).
- **Server**: The machine or program we send the request to, which provides the service.

## Request and Response

- A client sends a **request** asking for data or a service.
- A server sends a **response** replying to that request.

## Protocol

A protocol defines how a client and server communicate. This includes:

- Which commands the client and server both understand (for example, GET).
- How a request is structured (for example, first the command, then what you want).
- What syntax is used.
- Which response should be given for each type of request.

## Port

- A port identifies a specific service running on a system.
- When a client wants to use a service on a server, it must connect using the correct port.

## HTTP Methods

- The main documents that define HTTP are called RFCs (Request for Comments). They define 9 core commands.
- In HTTP, these commands are called **methods**:
    - GET
    - POST
    - PUT
    - DELETE
    - PATCH
    - HEAD
    - OPTIONS
    - CONNECT
    - TRACE

## Inspecting a Request

Using the browser's developer tools, we can see more details about a GET request:

- **Scheme**: Which protocol was used: HTTP or HTTPS.
- **Host**: The name of the host we requested resources from.
- **Filename**: Which file we requested. In our request this was `/`, which usually means the default page, `index.html`.
- **Address**: The IP address where the website is hosted. In this example, the website was hosted on the same device, so the address shown was `127.0.0.1`.
- **Status**: Whether the request was successful. Here we got `200 OK`, which means it was.

## Response

- When a request is sent, the server sends back a response.
- The response has two parts: the **response header** and the **response body**.
- The header contains metadata (information about the response), while the body contains the actual content that was requested.

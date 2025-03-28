# Internet

## How does the internet work?

The internet is a global network of interconnected computers and devices that communicate with each other to share information, resources, and services. There are two main concepts that are fundamental to the way the Internet functions: packets and protocols.

### Key Concepts

- **Networks**: Groups of connected computers that can send data to each other. The Internet itself is a network of networks.

- **Distributed Networking**: The Internet operates without a central control point, relying on a decentralized system where each connected device can communicate using standardized protocols.

- **Packet Switching**: Data sent over the Internet is divided into smaller segments called packets. Each packet travels independently across networks and is reassembled at its destination, optimizing the use of available bandwidth and enhancing reliability.

- **Protocols**: Standardized rules that dictate how data is transmitted and received over the Internet. Key protocols include:
  - **Internet Protocol (IP)**: Governs the addressing and routing of packets to ensure they reach the correct destination.
  - **Transmission Control Protocol (TCP)**: Ensures reliable delivery of packets in the correct order.
  - **Hypertext Transfer Protocol (HTTP)**: Facilitates the transfer of web pages and related content.

### Essential Networking Hardware

- **Routers**: Devices that forward data packets between computer networks, determining the optimal path for data to travel.

- **Switches**: Devices that connect multiple devices within a single network, facilitating internal communication.

- **Servers and Clients**: Servers store and provide data or services, while clients request and use these resources.

## What is HTTP?

HTTP (Hypertext Transfer Protocol) is a communication protocol used for transmitting data over the web. It allows web browsers (clients) and web servers to exchange information using a standardized request-response model. HTTP is stateless, meaning each request is independent, and the server does not retain information from previous interactions unless additional mechanisms (cookies, sessions) are used.

### How HTTP Works:

Client Sends a Request – A web browser requests a resource (e.g., a webpage) from a server by sending an HTTP request.

- **Server Processes the Request** – The server finds the requested resource and prepares a response.

- **Server Sends a Response** – The server sends back an HTTP response, which includes the requested content (e.g., HTML, images) and a status code (e.g., 200 OK, 404 Not Found).

- **Browser Displays the Content** – The browser renders the received data into a webpage.

### Key Features of HTTP:

Stateless – Each request is independent; servers don’t remember past interactions unless cookies, sessions, or tokens are used.

- **Text-Based** – HTTP messages are readable and consist of methods, headers, and body content.

- **Client-Server Model** – Clients (browsers) request information, and servers respond.

### HTTP Request

An HTTP request is a message sent by a client (e.g., a web browser) to request data from a server. It consists of:

- **Request Line** – Includes the HTTP method (e.g., GET, POST), the requested resource (URL), and the HTTP version.

- **Headers** – Provide additional details like the content type, user-agent, and authentication information.

- **Body (Optional)** – Contains data sent to the server, typically in POST and PUT requests.

### Common HTTP Methods:

- **GET** – Requests data from a server (e.g., load a webpage).

- **POST** – Sends data to the server (e.g., submitting a form).

- **PUT** – Updates existing data on the server.

- **DELETE** – Removes data from the server.

### HTTP Response

An HTTP response is a message sent by a server in response to a request. It contains:

- **Status Line** – Includes the HTTP version, status code, and status message.

- **Headers** – Provide metadata about the response, such as content type and server details.

- **Body (Optional)** – Contains the requested resource (e.g., HTML, JSON, or an error message).

### HTTP Status Codes

HTTP status codes indicate the outcome of a request:

- **1xx (Informational)** – The request is received, and processing is ongoing.

- **2xx (Success)** – The request was successfully processed (e.g., 200 OK).

- **3xx (Redirection)** – The requested resource has moved and requires further action (e.g., 301 Moved Permanently).

- **4xx (Client Errors)** – The client made an error in the request (e.g., 404 Not Found, 403 Forbidden).

- **5xx (Server Errors)** – The server encountered an issue while processing the request (e.g., 500 Internal Server Error).

### What is HTTPS?

HTTPS (Hypertext Transfer Protocol Secure) is the secure version of HTTP. It encrypts data using SSL/TLS, protecting it from hackers and ensuring secure communication, especially for sensitive transactions like online banking and e-commerce.

## What is a domain name?

A domain name is a string of letters and numbers that identifies a specific location or resource on the internet, like a website or email server. Instead of having to remember and type in an IP address, domain names provide a user-friendly way to access websites and other online resources.

### How it works:

When you type a domain name into your browser, the Domain Name System (DNS) translates it into the corresponding IP address, allowing your computer to connect to the correct server. E.g. google.com, mail.yahoo.com (This is a subdomain of yahoo.com)

### Structure:

Domain names are typically structured as follows:

- **Second-level domain (2LD):** The main part of the domain name (e.g., "google" in google.com).
- **Top-level domain (TLD):** The extension at the end of the domain name (e.g., ".com", ".org", ".net").
- **Subdomains:** A subdomain is a domain that is part of a larger domain (e.g., "mail" in mail.google.com).

## What is hosting?

Web hosting is essentially renting space on a computer (server) that's connected to the internet, allowing you to store all the files and data that make up your website. Without web hosting, your website's content (text, images, videos, etc.) would not be accessible to anyone on the internet. Besides providing storage, hosting providers often offer other services like domain name registration, email hosting, and website security tools.

### Types of Hosting:

- **Shared Hosting** – Multiple websites share server resources.

- **VPS (Virtual Private Server)** – A partitioned server offering more control.

- **Dedicated Hosting** – A single website has exclusive access to a server.

- **Cloud Hosting** – Scalable hosting using multiple servers.

## Browsers and how they work?

A browser is a software application that allows you to access and view websites on the internet. It retrieves web pages, displays text, images, and videos, and lets you interact with online content.

### How do Browsers Work?

- You enter a website address (URL) or click a link.
- The browser sends a request to the website’s server.
- The server responds by sending the webpage’s data (HTML, CSS, JavaScript, images, etc.).
- The browser processes this data and displays the webpage.
- You can interact with the page by clicking, scrolling, or entering information.

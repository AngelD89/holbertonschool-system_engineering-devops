# 0. Simple Web Stack Infrastructure

## Description
This project presents a basic one-server web infrastructure used to host a website reachable via **www.foobar.com**.  
The goal is to understand how core web components interact, starting from a user request to the server response, and to identify the limitations of such a simple setup.

This infrastructure is commonly referred to as a **simple web stack** and is suitable for low-traffic websites.

---

## Infrastructure Overview

The infrastructure consists of **one server** with the following components:

- **Domain name:** foobar.com  
- **DNS record:** `www` (A record) pointing to IP address `8.8.8.8`
- **Web server:** Nginx
- **Application server**
- **Application files:** Code base
- **Database:** MySQL

---

## Request Flow

1. A user enters `www.foobar.com` in a web browser.
2. DNS resolves `www.foobar.com` to the IP address `8.8.8.8`.
3. The browser sends an HTTP/HTTPS request to the server.
4. The **Nginx web server** receives the request.
5. Nginx forwards the request to the **application server**.
6. The application server executes the application logic.
7. If required, the application queries the **MySQL database**.
8. The response is sent back through Nginx to the user’s browser.

---

## Components Explained

### Server
A server is a machine (physical or virtual) that hosts applications, stores data, and responds to requests over a network.

### Domain Name
The domain name provides a human-readable address that maps to an IP address, allowing users to access the server easily.

### DNS Record
The `www` record is an **A record**, which maps the domain name directly to an IPv4 address.

### Web Server (Nginx)
- Handles HTTP/HTTPS requests
- Serves static content
- Acts as a reverse proxy to the application server

### Application Server
- Runs the application logic
- Processes dynamic requests
- Communicates with the database

### Database (MySQL)
- Stores persistent data
- Handles data queries and transactions

### Communication Protocol
The server communicates with the user’s computer using **HTTP or HTTPS over TCP/IP**.

---

## Infrastructure Limitations

### Single Point of Failure (SPOF)
Since all components are hosted on one server, if the server fails, the entire website becomes unavailable.

### Downtime During Maintenance
Maintenance tasks such as deploying new code or restarting services cause downtime because there is no redundancy.

### Lack of Scalability
This infrastructure cannot handle high traffic efficiently because all requests are processed by a single server.

---

## Diagram

A diagram illustrating this infrastructure has been created and uploaded separately as required.  
The link to the diagram screenshot is included in the answer file for this task.

---

## Author
**Angel D Bayo Torres**

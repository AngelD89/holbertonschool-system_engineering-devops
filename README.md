# Web Infrastructure Design

## Project Overview
This project explores the design of web infrastructures of increasing complexity.  
Each task builds on the previous one to improve **availability, security, scalability, and reliability**.

The goal is to understand how core infrastructure components interact and why additional elements are introduced at each stage.

---

## Task 0: Simple Web Stack

### Description
A basic one-server web infrastructure hosting **www.foobar.com**.

### Components
- 1 server
- Nginx (web server)
- Application server
- Application code base
- MySQL database
- DNS A record pointing `www.foobar.com` to the server IP

### Characteristics
- Simple and low cost
- Single Point of Failure (SPOF)
- No scalability
- Downtime during maintenance

---

## Task 1: Distributed Web Infrastructure

### Description
A three-server infrastructure introducing a load balancer and database replication.

### Added Components
- HAProxy load balancer
- Second backend server
- MySQL Primary-Replica (Master-Slave) setup

### Load Balancer
- Algorithm: Round Robin
- Setup: Active-Active

### Database
- Primary handles write operations
- Replica handles read operations

### Limitations
- Load balancer is a SPOF
- Primary database is a SPOF
- No security or monitoring

---

## Task 2: Secured and Monitored Infrastructure

### Description
The infrastructure is secured, serves encrypted traffic, and is monitored.

### Added Components
- 3 firewalls
- SSL certificate for HTTPS
- 3 monitoring agents

### Security
- Firewalls restrict network access
- HTTPS encrypts data in transit and protects user information

### Monitoring
- Monitoring agents collect logs and metrics
- Data is sent to a monitoring service
- Web server QPS is monitored using request metrics from Nginx

### Limitations
- SSL termination at the load balancer exposes internal traffic
- Only one database accepts writes
- Servers run multiple components, making scaling harder

---

## Task 3: Scale Up Infrastructure

### Description
The infrastructure is scaled for higher availability and better separation of concerns.

### Added Components
- Additional server
- Second HAProxy configured as a load balancer cluster
- Dedicated servers for:
  - Web server
  - Application server
  - Database server

### Benefits
- Load balancer redundancy
- Independent scaling of each layer
- Improved performance and maintainability
- Reduced impact of failures

---

## Key Concepts Covered
- DNS and load balancing
- Web server vs application server
- Database replication
- Firewalls and HTTPS
- Monitoring and performance metrics
- Scalability and fault tolerance

---

## Author
**Angel D Bayo Torres**

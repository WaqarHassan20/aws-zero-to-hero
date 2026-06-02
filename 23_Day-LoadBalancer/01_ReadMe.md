### What is Load Balancer?

- Load Balancer is a device that distributes network or application traffic across a number of servers. It helps to improve the performance and reliability of applications by distributing the workload evenly across multiple servers.
- Load Balancer can be hardware hardware, software, or a combination of both.
- Load Balancer can be used to balance the load across multiple servers, which helps to improve the performance and reliability of applications.
- Load Balancer can be used to distribute the load across multiple servers, which helps to improve the performance and reliability of applications.
- e.g - AWS Elastic Load Balancing (ELB), Azure Load Balancer, Google Cloud Load Balancing, etc.
- Real life use of LB : Let's suppose you have a website that receives a lot of traffic. If you have only one server, it may become overwhelmed and unable to handle all the requests. By using a load balancer, you can distribute the traffic across multiple servers, which helps to improve the performance and reliability of your website.


### Types of Load Balancer:

1. **Layer 4 LB | Network Load Balancer**: 

- A Network Load Balancer (NLB) works at Layer 4 (Transport Layer) of the OSI model. This means it makes routing decisions based on IP addresses, TCP/UDP ports, and protocols, without looking inside the actual data (payload).
- It is designed for ultra-high performance and low latency.
- Can handle millions of requests per second with very fast response times.
- Supports TCP, UDP, and TLS traffic.
- It does not understand HTTP/HTTPS content, so it cannot do things like URL-based routing.
- Best used for:
- Real-time systems (gaming, streaming)
- High-performance APIs
- Applications needing static IP addresses
- It preserves the original client IP, which is useful for logging and security.
- In short: NLB is fast and powerful, but “dumb” — it only sees network-level info.

2. **Layer 7 LB | Application Load Balancer**: 

- An Application Load Balancer (ALB) works at Layer 7 (Application Layer), which means it understands the actual content of requests, especially HTTP/HTTPS.
- It can make intelligent decisions based on:
- URL paths (/api, /login)
- Hostnames (api.example.com)
- Headers, cookies, query parameters
- Supports advanced routing like:
- Path-based routing
- Host-based routing
- Ideal for:
- Web applications
- Microservices architecture
- REST APIs
- Supports WebSockets and HTTP/2
- Provides features like:
- Authentication (e.g., via OAuth)
- SSL termination (handles HTTPS for you)
- In short: ALB is smart and flexible, perfect for modern web apps.

3. **GW LB | Gateway Load Balancer**: 

- A Gateway Load Balancer (GWLB) is used for network security and traffic inspection, combining load balancing with routing through security appliances.
- Works at Layer 3 (Network Layer) with some Layer 4 awareness.
- Designed to route traffic through third-party virtual appliances, such as:
- Firewalls
- Intrusion Detection/Prevention Systems (IDS/IPS)
- Deep packet inspection tools
- Uses GENEVE protocol to encapsulate and forward traffic to appliances.
- Key features:
- Transparent insertion of security devices
- Auto scaling of security appliances
- Centralized traffic inspection
- Best used in:
- Enterprise networks
- Cloud security architectures
- Zero-trust environments
- In short: GWLB is not for serving users directly — it’s for securing and inspecting traffic.
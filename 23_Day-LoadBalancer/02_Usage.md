1. **Layer 4 LB | Network Load Balancer**: 

Use when you need maximum speed and low latency and don’t care about request content.
Best for:

- TCP/UDP apps (games, streaming, real-time systems)
- Handling millions of connections
- When you need static IP or preserve client IP
- Choose NLB when performance > intelligence

1. **Layer 7 LB | Application Load Balancer**: 

Use when your app is web-based (HTTP/HTTPS) and needs smart routing.
Best for:

- Websites, REST APIs, microservices
- Routing based on URL, domain, headers
- When you need features like auth, SSL handling
- Choose ALB when intelligence > raw speed

3. **GW LB | Gateway Load Balancer**: 

Use when you need to inspect and secure traffic, not just distribute it.
Best for:

- Firewalls, IDS/IPS, security appliances
- Centralized traffic inspection in cloud
- Enterprise or zero-trust architectures
- Choose GWLB when security & inspection is the goal
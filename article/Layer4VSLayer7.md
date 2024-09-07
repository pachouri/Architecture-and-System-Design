# Layer4 vs Layer7 Load balancer


![alt text](https://github.com/pachouri/Architecture-and-System-Design/blob/main/diagram/L4_VS_L7_LB.gif?raw=true)
**Layer 4 Load Balancer (Transport Layer)**
- **Operation**: Works at the transport layer, specifically at TCP (Transmission Control Protocol) or UDP (User Datagram Protocol) level.
- **Routing**: It makes routing decisions based on IP addresses and ports. It doesn’t inspect the actual content of the packets beyond this information.
- **Performance**: Generally faster than Layer 7 load balancers because it doesn't perform deep packet inspection (DPI) or interpret application-level data.
- **Use Case**: Ideal for scenarios where raw speed and handling of large volumes of traffic are critical, such as balancing traffic between application servers without inspecting individual HTTP requests.
- **Examples**: TCP load balancing for applications like databases, VPNs, etc.

**Layer 7 Load Balancer (Application Layer)**

- **Operation**: Operates at the application layer, where it can understand and interpret the content of requests, such as HTTP, HTTPS, or other application protocols.
- **Routing**: It can make more advanced routing decisions, like forwarding requests based on URL paths, headers, cookies, and even the content of the message itself (e.g., HTTP request bodies).
- **Performance**: Slightly slower than Layer 4 load balancers due to the overhead of deep packet inspection and more complex decision-making.
- **Use Case**: Perfect for applications where you need more control over traffic distribution, such as web applications where routing based on URL paths, headers, or content is required.
- **Examples**: HTTP/HTTPS load balancing for web servers, API gateways, microservices, etc.

**Key Differences**

| **Feature** | **Layer4** | **Layer7** |
| --- | --- | --- |
| OSI Layer | Transport | Application |
| Decision Criteria | IP, Port | URL, Header, Cookies |
| Traffic Control | Basic | Advance( Content Based) |
| Speed | Faster | Slower |
| SSL/TLS Termination | Not Supported | Supported |
| Use Case | Simpe, High Throughput | Complex, Application Based Routing |

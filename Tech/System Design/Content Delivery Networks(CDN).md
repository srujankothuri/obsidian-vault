---
aliases:
  - cdn
  - CDN
---

A content delivery network (CDN) is a group of servers spread out over a region or around the world that work together to speed up content delivery on the web. The servers in a CDN temporarily store (or [cache](https://www.cloudflare.com/learning/cdn/what-is-caching/)) webpage content like images, HTML, JavaScript, and [video](https://www.cloudflare.com/learning/video/what-is-video-cdn/). They send the cached content to users who load the webpage. Today, almost all websites and applications rely on a CDN to help serve content to their users.

Web applications use CDNs largely because they offer four important benefits: better performance, increased reliability, cost savings, and [resilience](https://www.cloudflare.com/the-net/security-signals/building-cyber-resiliency/) against cyber attacks.

#### Performance

Faster performance is the benefit most people think of when considering CDNs, and for good reason. Websites that start using a CDN have seen [50% reductions in load times](https://www.cloudflare.com/case-studies/ypo/), or even more in some cases. CDNs speed up content delivery by:

- Decreasing the distance between where content is stored and where it needs to go
    
- Reducing file sizes to increase load speed
    
- Optimizing server infrastructure to respond to user requests more quickly

#### Reliability

Sometimes, things go wrong on the Internet. Servers go down, networks become congested, and connections get interrupted. A CDN enables web applications to provide uninterrupted service to users even in the face of these problems.

CDNs [balance the load](https://www.cloudflare.com/learning/performance/what-is-load-balancing/) of network traffic, ensuring no one server gets overwhelmed. In the event that a single server stops working, a CDN can initiate a "[failover](https://www.cloudflare.com/learning/performance/what-is-server-failover/)" process that allows a backup server to take over. Some CDNs, like the [Cloudflare CDN](https://www.cloudflare.com/application-services/products/cdn/), can [route around network congestion](https://www.cloudflare.com/products/argo-smart-routing/), like GPS navigation software finding a way around heavy freeway traffic.
  
#### Cost savings

The main way that CDNs cut down on expenditure for website operators is by reducing trips to and from the [origin server](https://www.cloudflare.com/learning/cdn/glossary/origin-server/). Because CDNs cache much of the content on a website and serve that content from the cache, the origin server does not have to deliver the same content over and over. Instead, the CDN does this on the origin server's behalf.

Web hosting providers typically charge websites for the data that gets transferred to and from the web host. The more data that gets transferred, the greater the cost. People often refer to these expenses as "bandwidth costs," even though "bandwidth" really refers to network capacity.

But when a CDN serves most of a website's content on the origin server's behalf, far less data needs to be transferred. Fewer user requests go to the origin server, because the CDN handles most of them. And less content goes out from the origin server for the same reason, lowering bandwidth costs.

#### Resilience against attack

CDNs are especially well-suited to defending websites from [[Denial Of Service(Dos)]](https://www.cloudflare.com/learning/ddos/glossary/denial-of-service/)and  [[Denial Of Service(Dos)#DDoS| DDoS]]  ([distributed denial-of-service (DDoS)](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/))  attacks. In these attacks, an attacker directs vast quantities of junk network traffic at a website to try to overwhelm and crash the website. With their many servers, CDNs are better able to absorb large amounts of traffic, even unnatural traffic spikes from a DDoS attack, than a single origin server. By doing so, they keep websites online even when under attack.
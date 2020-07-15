### Azure CDN

![Azure CDN](https://docs.microsoft.com/en-us/azure/cdn/media/cdn-overview/cdn-overview.png)

Caches static content on edge server to icrease the performance by making latency low.

### Features
- Dynamic site acceleration
- Media, Web, Text, Larg files delivery
- Dynamic content routing optimization

### Important Terms
- Edge Server
- Origin Server
- Point of presence (POP)
- Border Gateway Protocol (BGP)

#### Azure front door
> Front Door works at Layer 7 or HTTP/HTTPS layer and uses anycast protocol with split TCP and Microsoft's global network for improving global connectivity.

Simalar Services

1. Traffic Manager
2. Application Gateway (Application layer load balancer)
3. Load Balancer (Network layer load balancer)

Azure CDN provides fast content delivery to the closest users. It works in a way like if some content is being request frequently it store or cache the content
on edge servers. All that request will be serve from edge servers rather than origin servers. Hence it improve performance and make latency low.

Reference:
https://microsoft.github.io/AzureTipsAndTricks/

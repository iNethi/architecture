# iNethi Architecture
Explanation of the iNethi system

## Architecture Types
There are two iNethi architectures. Each has advantages and tradeoffs. There is a hybrid architecture (diagram 1) and a 
local architecture (diagram 2).

**Diagram 1**

<img src="diagrams/iNethi-mixed-architecture-overview.png" alt="hybrid architecture diagram" width="400"/>

**Diagram 2**

<img src="diagrams/iNethi-local-architecture-overview.png" alt="local architecture diagram" width="400"/>

In the above diagrams the mandatory docker services are detailed for a fully functional iNethi instance. Whether they 
are locally hosted or hosted on a cloud server. When using the iNethi builder the services installed as system 
requirements are:
- Traefik
- Prometheus
- Grafana
- InfluxDB
- Blackbox 

### Differences in Architecture
The hybrid architecture differs from the local architecture in one key way, [Keycloak](https://www.keycloak.org/) and 
[RadiusDesk](https://github.com/RADIUSdesk) are hosted on a cloud server (AWS in our case). 

Advantages of a hybrid architecture:
- This allows admin users to manage multiple networks from one place. RadiusDesk vouchers for internet access can be 
generated that can be used for access to multiple networks, enabling seamless roaming between networks
- Keycloak accounts can be used for authentication at different networks and for global and local access to iNethi services
using the same username and password creating a single sign on environment (SSO), more on this later.

Disadvantages of a hybrid architecture
- Constant need for an uplink to the internet to validate users SSO status and voucher usage/access. If there is no
access then users will not be able to access any network architecture that utilises Keycloak and RadiusDesk

### Differences to Users

## the iNethi App

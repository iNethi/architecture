# iNethi App
The iNethi app is a Reactive Native App with the purpose of bringing all iNethi services into one space.

## Populating the Home Page
The home page of the app populates with buttons for various services and divides them into sections based on the
service's characteristics. This is dynamic. The buttons rendered adn the locations they point to depends on whether the
user has an Internet connection, whether the user is connected to an iNethi Community Network and what services are 
available if they are. The user cases are detailed below.

### Connected to an iNethi Network
The user is connected to an iNethi network.

<img src="diagrams/inethi-app-connected.png" alt="hybrid architecture diagram" width="600"/>

#### Explanation
- _API Call 1_: This is a call to the locally hosted [User management API](https://github.com/iNethi/manage-backend) 
requesting the available services offered by the local server.
- _API Call 2_: This is a call to the cloud hosted [User management API](https://github.com/iNethi/manage-backend) 
requesting the available services offered by the global server.

For any overlapping services the local service will be given priority.

### Not Connected to an iNethi Network
The user is connected to an external network.
<img src="diagrams/inethi-app-not-connected.png" alt="hybrid architecture diagram" width="600"/>

#### Explanation
- _API Call 1_: This is a call to the locally hosted [User management API](https://github.com/iNethi/manage-backend)
  requesting the available services offered by the local server. This request will not resolve.
- _API Call 2_: This is a call to the cloud hosted [User management API](https://github.com/iNethi/manage-backend)
  requesting the available services offered by the global server.

Given the local request did not resolve only the services offered globally will be listed.

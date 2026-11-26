# Putting It All Together

- To sum up: when you request a website, your computer first needs the IP address of the server it should talk to, and it gets this using DNS.
- Your computer then talks to the web server using the HTTP protocol. The web server sends back HTML, JavaScript, CSS, images, etc., which your browser uses to build and display the website for you.

## Load Balancers

- A load balancer receives the requests meant for a website and decides which of the multiple servers should handle each one.
- If one of the servers starts acting up, it switches traffic to the next working server.
- It also does periodic health checks to make sure all the servers are responding correctly.
- It shares out requests using different methods (algorithms), for example:
    1. **Round-robin**: sends requests to each server in turn.
    2. **Least connections**: checks how many requests each server is currently handling and sends the new request to the least busy one.
    3. **Weighted**: gives more powerful servers a bigger share of the requests.

## CDN (Content Delivery Network)

- It's an excellent way to cut down traffic to a busy website.
- It checks where a request is coming from and finds the nearest server that has a copy of the website's files.
- The request is then served from there, instead of having to potentially travel to the other side of the world.

## Databases

- Web servers communicate with databases to store and fetch data.

## WAF (Web Application Firewall)

- It sits between the user's web request and the web server.
- It uses techniques like rate limiting (capping how many requests one user can send) to identify bot requests and malicious threat actors, and drops their requests.
- This way, the server is protected not only from malicious requests but also from being overloaded.

# How Web Servers Work

## Web Server

- A web server is software that listens for incoming connections and then uses the HTTP protocol to deliver web content to its clients.
- The most common web server software is Apache, Nginx, IIS and NodeJS.
- A web server delivers files from what is called its **root directory**.
- If you host multiple websites on one server using **virtual hosts**, you can set an independent root directory for each website.

## Static and Dynamic Content

- Static content is content on a web page that doesn't change, like a fixed image or a CSS file.
- Dynamic content is content that does change, like a search bar changing its suggestions as you start typing.

# nginx-real-world-configs
A hands on project to learn and implement NGINX concepts such as hosting websites, configuring multiple sites, and setting up reverse proxy servers.

#### What is nginx?
NGINX (pronounced “engine-x”) is a high performance web server that is widely used to serve websites and manage internet traffic efficiently. It can function not only as a web server for delivering static content like HTML, CSS, and JavaScript files, but also as a reverse proxy that forwards client requests to backend servers such as Node.js or PHP applications. Additionally, NGINX can act as a load balancer, distributing incoming traffic across multiple servers to improve performance and reliability. It is known for its speed, scalability, and low resource usage, making it a popular choice for modern web applications and production environments.

#### Project Agenda
- Understand the fundamentals of NGINX and its architecture
- Set up NGINX as a web server to host static websites
- Configure multi-site hosting (serve multiple websites from a single server)
- Implement reverse proxy to route client requests to backend servers
- Explore load balancing techniques to distribute traffic across multiple servers
- Work with NGINX configuration files (nginx.conf, server blocks)
- Monitor and analyze access logs and error logs for debugging
- Understand basic security practices (headers, request handling)
- Gain hands-on experience with real-world deployment scenarios
- Build a strong foundation in DevOps and server management concepts

### Project Overview

### Static Web Hosting Configuration with NGINX
- Install nginx on server (EC2) instance
- Allow access from HTTP with default port and SSH (Secure Shell) to securely connect to and control a remote server over the internet.
- Verified nginx installed or not by accessing server ip using HTTP over internet.
- <img width="1861" height="694" alt="Screenshot 2026-05-01 000919" src="https://github.com/user-attachments/assets/7be31ac1-2584-42cd-8c4e-cb0f375834af" />
- Updates index.html inside /usr/share/html/index.html with new index.html
- Modified the NGINX configuration to set the root directory to /usr/share/nginx/html, enabling the server to serve static web content from this location.
- <img width="1226" height="205" alt="Screenshot 2026-05-01 001952" src="https://github.com/user-attachments/assets/a98d516d-a807-470b-abdc-d743e2a48cf4" />
- Reload nginx service and restart nginx , And access server public ip with default port
- And here is result
- <img width="1865" height="967" alt="Screenshot 2026-05-01 002041" src="https://github.com/user-attachments/assets/62d031eb-a3f6-4666-9c89-9c55cc25fb37" />

### Serving Multiple Websites on a Single NGINX Server
- Install nginx on server (EC2) instance
- Allow access from HTTP with default port and SSH (Secure Shell) to securely connect to and control a remote server over the internet.
- Verified nginx installed or not by accessing server ip using HTTP over internet.
- <img width="1861" height="694" alt="Screenshot 2026-05-01 000919" src="https://github.com/user-attachments/assets/7be31ac1-2584-42cd-8c4e-cb0f375834af" />
- Created two folder inside /usr/share/nginx/html/ web1.com and web.com
- For both folder created index.html and style.css
-  Configured NGINX to serve multiple websites using location blocks with alias directives, mapping /web1.com and /web2.com to their respective directories inside /usr/share/nginx/html.
-  And here is result
- <img width="1856" height="955" alt="Screenshot 2026-05-01 124433" src="https://github.com/user-attachments/assets/e5395f66-d50b-4b95-8c59-8a5361355c68" />
- <img width="1845" height="962" alt="Screenshot 2026-05-01 124448" src="https://github.com/user-attachments/assets/2941a90c-96dc-42c3-a224-564044d59120" />


### NGINX Access and Error Logs
- Access Logs record every request made to the server. They include details like client IP address, request method (GET/POST), requested URL, response status code (200, 404, etc.), and user agent. These logs are useful for analyzing traffic and monitoring website usage.
- Error Logs store information about issues that occur on the server, such as failed requests, configuration errors, or server crashes. They help in debugging and troubleshooting problems in the application or server setup\
- NGINX logs are stored in /var/log/nginx/, including access.log and error.log.
- <img width="1864" height="816" alt="Screenshot 2026-05-01 164251" src="https://github.com/user-attachments/assets/d3e8ec9a-0d97-4b80-af13-901461e6c9d6" />
- <img width="1874" height="816" alt="Screenshot 2026-05-01 164305" src="https://github.com/user-attachments/assets/11a6f625-b704-4b4d-b238-99490f36107a" />

### Implementing Reverse Proxy with NGINX
- Launch 2 server , one for nginx server(Reverse proxy) and another for web server(actual web server)
- Install nginx on nginx server and install apache2 on (web server) 
- Modified configuration file by passing proxy at web server ip and allow HTTP access on web server with only nginx server ip
- <img width="1202" height="802" alt="Screenshot 2026-05-02 122148" src="https://github.com/user-attachments/assets/50fc174c-0359-4f04-ac0d-9fe9b16aaee1" />
- And result is here
- <img width="1850" height="962" alt="Screenshot 2026-05-02 122210" src="https://github.com/user-attachments/assets/53f82a68-0a31-47d7-b5fa-5e98c36b0b4c" />





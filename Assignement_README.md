# Travel Memory App - DevOps Deployment

##  Project Overview
This project demonstrates deployment of a full-stack application using AWS and DevOps practices.

---

##  Architecture
- AWS EC2 (Multi-AZ)
- Application Load Balancer
- Nginx (Reverse Proxy)
- Node.js Backend
- React Frontend
- MongoDB Atlas
- Cloudflare (DNS + SSL)

---

##  Features Implemented
- Multi-EC2 deployment across Availability Zones
- Load balancing using ALB
- Domain mapping using Cloudflare
- HTTPS enabled using Flexible SSL
- Reverse proxy using Nginx

---

##  Domain
http://mytravelapp.online  
https://mytravelapp.online  

---

##  Testing
- Verified load balancing using `/test` endpoint
- Confirmed traffic distribution across EC2 instances

---

##  Screenshots
(Attach in report)

---

##  Challenges Faced
- Nginx routing issue (404)
- Load balancer routing only one instance
- Cloudflare DNS conflicts
- Backend validation errors

---

##  Conclusion
Successfully deployed scalable and highly available application using AWS and Cloudflare.

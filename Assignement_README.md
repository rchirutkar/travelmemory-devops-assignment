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

## Diagram

                                                  🌐 User (Browser)
                                                         │
                                                         ▼
                                      ┌──────────────────────────────────────┐
                                      │  Cloudflare (DNS + SSL)              │
                                      │  mytravelapp.online                  │
                                      └──────────────────────────────────────┘
                                                         │
                                                         ▼
                                      ┌──────────────────────────────────────┐
                                      │ AWS Region (ap-south-1)              │
                                      │                                      │
                                      │   ┌──────────────────────────────┐   │
                                      │   │ Application Load Balancer    │   │
                                      │   │ (HTTP:80 Listener)           │   │
                                      │   └──────────────┬───────────────┘   │
                                      │                  │                   │
                                      │         ┌────────▼────────┐          │
                                      │         │  Target Group   │          │
                                      │         └───────┬─────────┘          │
                                      │                 │                    │
                                      │   ┌─────────────┴─────────────┐      │
                                      │   │                           │      │
                                      │   ▼                           ▼      │
                                      │ ┌──────────────┐    ┌──────────────┐ │
                                      │ │ AZ-1         │    │ AZ-2         │ │
                                      │ │ (ap-south-1a)│    │ (ap-south-1b)│ │
                                      │ │              │    │              │ │
                                      │ │ EC2 Instance │    │ EC2 Instance │ │
                                      │ │ ───────────  │    │ ───────────  │ │
                                      │ │ SecurityGrp  │    │ SecurityGrp  │ │
                                      │ │ Nginx        │    │ Nginx        │ │
                                      │ │ (Proxy)      │    │ (Proxy)      │ │
                                      │ │ ↓            │    │ ↓            │ │
                                      │ │ Node.js App  │    │ Node.js App  │ │
                                      │ └──────────────┘    └──────────────┘ │
                                      │                                      │
                                      └──────────────────────────────────────┘
                                                         │
                                                         ▼
                                              ┌──────────────────────┐
                                              │ MongoDB Atlas        │
                                              │ (Cloud Database)     │
                                              └──────────────────────┘

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

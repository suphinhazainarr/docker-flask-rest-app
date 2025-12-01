# docker-flask-rest-app
Dockerized Flask REST API with MySQL and Redis using Docker Compose | DevOps Automation Project


# Flask REST Application with Docker and Docker Compose

This project demonstrates how to containerize and deploy a Python Flask REST API using Docker and Docker Compose.  
It includes multi-container architecture with two Flask app instances, a MySQL database, and a Redis cache system.  
This fulfills the complete requirement of DevOps automation, scalability and service communication.

---

## Project Objectives

- Build a Docker image for a Python Flask REST application
- Deploy multi-container architecture using Docker Compose
- Run two instances of the application to simulate scaling
- Integrate MySQL database to store palindromes
- Integrate Redis caching for hit counter functionality
- Ensure automatic restart of containers unless manually stopped
- Host and access application over HTTP through EC2 server

---

## Technologies Used

| Technology | Purpose |
|-----------|---------|
| Docker | Containerization |
| Docker Compose | Multi-service orchestration |
| Python Flask | Application framework |
| MySQL | Persistent data storage |
| Redis | Cache memory for API hit tracking |
| Linux / Amazon EC2 | Hosting environment |

---

## Application Endpoints

| Endpoint | Purpose |
|---------|---------|
| `/` | Returns “Hello World” |
| `/status` | Health check (200 OK when app ready) |
| `/palindrom/<text>` | Checks and stores palindrome text in DB |
| `/admin` | Displays stored palindromes |
| `/redis-hits` | Shows Redis hit count (confirms Redis connection) |
| `/prepare-for-deploy` | Pre-deployment response |
| `/ready-for-deployment` | Confirms service is ready |

---

## Repository Structure

flask-app/
│
├── Dockerfile
├── docker-compose.yml
├── app.py
├── create_db.py
├── drop_db.py
└── requirements.txt


## Configuration Notes

- All configuration is done via Docker Compose environment variables
- Database and Redis services start before Flask app using `depends_on`
- MySQL credentials match application `DATABASE_URI`

# Multi-App Node.js Landing Page (Docker Compose Setup)

This project demonstrates running **multiple Node.js web applications** using **Docker Compose**.  
Each app serves the same static landing page but runs as a separate container with different environment variables and ports.

---

## 📁 Project Structure


├── Dockerfile
├── docker-compose.yml
├── index.html
├── package.json
└── server.js


---

## ⚙️ How It Works

- **Docker Compose** defines three independent services (`app1`, `app2`, `app3`), each running from the same image but using a unique environment variable `APP_NAME` and port mapping.
- **Express.js** (in `server.js`) serves the `index.html` landing page and listens on port `3000` inside the container.
- Each container exposes a different host port:
  - `App1` → [http://localhost:3001](http://localhost:3001)
  - `App2` → [http://localhost:3002](http://localhost:3002)
  - `App3` → [http://localhost:3003](http://localhost:3003)

---

## 🧱 Prerequisites

Before running the project, make sure you have:

- [Docker](https://docs.docker.com/get-docker/) installed  
- [Docker Compose](https://docs.docker.com/compose/) available  
- Node.js (optional, for local development)

---

## 🚀 Running the Project

### 1. Build and start containers
```bash
docker-compose up --build


2. Access your apps

App  URL
App1 http://localhost:3001
App2 http://localhost:3002
App3 http://localhost:3003

Each will serve the same landing page but can behave differently if configured via environment variables.

Environment Variables

APP_NAME Name of the application (used inside server.js)  App1, App2, App3 respectively

You can modify these in the docker-compose.yml file.

Tech Stack
	•	Node.js 18
	•	Express.js
	•	Docker Compose
	•	HTML/CSS (Minimal Landing Page Template)

Development (Without Docker)

If you want to test locally without Docker:

npm install
node server.js

http://localhost:3000

Stopping Containers

To stop running containers:

docker-compose down

To remove all containers and images:

docker-compose down --rmi all

Notes
	•	This setup is great for experimenting with multi-service deployments using a single codebase.
	•	You can extend it by adding a reverse proxy (NGINX) or load balancer in front of the apps.
	•	The landing page (index.html) is lightweight and responsive.

    
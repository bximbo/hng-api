# HNG Stage 1 DevOps API

This project is a simple REST API built for the HNG DevOps Stage 1 task. It demonstrates basic API development, deployment on a Linux VPS, and reverse proxy configuration using Nginx.

---

## Live URL

[http://23.20.35.23](http://23.20.35.23)

---

## Project Overview

This API provides three endpoints:

- `/` → returns a status message
- `/health` → returns service health status
- `/me` → returns user profile information

The application is built using Node.js and Express and is deployed on an Ubuntu server using PM2 for process management and Nginx as a reverse proxy.

---

## Tech Stack

- Node.js
- Express.js
- PM2 (Process Manager)
- Nginx (Reverse Proxy)
- Ubuntu Server (VPS)

---

## API Endpoints

### GET /

Response:

```json
{
  "message": "API is running"
}
```

---

### GET /health

Response:

```json
{
  "message": "healthy"
}
```

---

### GET /me

Response:

```json
{
  "name": "Israel Abimbola Adenuga",
  "email": "israelabimbolaa@gmail.com",
  "github": "https://github.com/bximbo"
}
```

---

## Local Setup

### Clone repository

```bash
git clone https://github.com/bximbo/hng-stage1-api.git
cd hng-stage1-api
```

### Install dependencies

```bash
npm install
```

### Run the application

```bash
node index.js
```

The server runs on:

```
http://localhost:3000
```

---

## Deployment Architecture

Client → Nginx (port 80) → Node.js App (port 3000 via PM2)

- Nginx handles incoming HTTP requests
- PM2 ensures the application stays running
- Node.js serves the API

---

## Process Management

The application is managed using PM2:

```bash
pm2 start index.js --name hng-api
pm2 save
pm2 startup
```

This ensures the service restarts automatically on server reboot.

---

## Notes

- The application does not expose port 3000 publicly
- All traffic is routed through Nginx
- All endpoints return application/json with HTTP 200 status

---

## Author

Israel Abimbola Adenuga 
GitHub: [https://github.com/bximbo](https://github.com/bximbo) 
Email: [israelabimbolaa@gmail.com](mailto\:israelabimbolaa@gmail.com)


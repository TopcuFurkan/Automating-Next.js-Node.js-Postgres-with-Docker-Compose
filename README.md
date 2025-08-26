# Automating-Next.js-Node.js-Postgres-with-Docker-Compose
Docker Compose setup to run Next.js, Node.js, and PostgreSQL with .env support for easy on-prem or local deployments.

## Setup and Usage

1. Prepare your .env files inside each app directory:
   nextjs-app/.env
   nodejs-app/.env

2. Start the containers:
   docker compose up -d

3. Next.js frontend: http://localhost:3000
   Node.js backend: http://localhost:4000 (or port 8082 as configured)

4. Manage containers:
   docker compose down

5. View logs:
   docker compose logs -f nextjs-app
   docker compose logs -f nodejs-app
   docker compose logs -f postgres-db

6. Rebuild after changes:
   docker compose up -d --build

Notes:
.env files are required and must be mounted into the containers.
PostgreSQL data is persisted in the Docker volume pgdata.
All images are pulled directly from Docker Hub.
This setup avoids hardcoding sensitive information in Docker images.
The setup ensures automatic restart for containers (unless-stopped) and is ready for on-premises or local deployment.
 

# Docker Voting Application

A simple voting application project using Docker Compose, a backend API, and a MySQL database. The project demonstrates how to run application and database services in separate Docker containers.

## Project Overview

The application uses Docker to containerize its services and Docker Compose to manage them together.

### Technologies Used

- **Docker** — Containerizes the application.
- **Docker Compose** — Runs and manages multiple containers.
- **MySQL 8.4** — Stores application data.
- **Backend API** — Handles application requests on port `5000`.
- **SQL** — Initializes the database schema.

## Project Structure

```text
docker-voting-2/
├── database/
│   └── init.sql
├── docker-compose.yaml
└── README.md
```

| File | Description |
|---|---|
| `database/init.sql` | Contains SQL statements for database initialization. |
| `docker-compose.yaml` | Defines and configures the application and database services. |
| `README.md` | Documents the project and setup instructions. |

## Prerequisites

Make sure you have installed:

- Docker
- Docker Compose
- Git

Verify your installations:

```bash
docker --version
docker compose version
git --version
```

## Getting Started

### 1. Clone the repository

```bash
git clone git@github.com:joelprinesh2026/docker-voting-2.git
```

### 2. Navigate to the project directory

```bash
cd docker-voting-2
```

### 3. Start the containers

```bash
docker compose up -d --build
```

This command builds the application image if required and starts the services in the background.

### 4. Check the running containers

```bash
docker compose ps
```

### 5. View application logs

```bash
docker compose logs -f
```

Press `Ctrl+C` to stop viewing the logs. This does not stop the containers.

### 6. Access the backend

If the Compose configuration maps host port `5000` to container port `5000`, open:

http://localhost:5000

The exact response depends on the backend routes configured in the application.

## Database Initialization

The SQL file is located at:

```text
database/init.sql
```

Check `docker-compose.yaml` to confirm that the SQL file is mounted into the MySQL initialization directory.

**Note:** MySQL initialization scripts normally run when the database data directory is first initialized. If an existing database volume is reused, changes to `init.sql` may not run automatically.

## Useful Docker Commands

Check running containers:

```bash
docker compose ps
```

View logs:

```bash
docker compose logs -f
```

View backend logs:

```bash
docker compose logs -f backend
```

Stop the containers:

```bash
docker compose down
```

Stop containers and remove their volumes:

```bash
docker compose down -v
```

**Warning:** The last command removes Compose-managed volumes and may permanently delete your stored database data.

## Learning Objectives

- Understand Docker containers and images.
- Configure multiple services using Docker Compose.
- Connect a backend application to a MySQL database.
- Initialize a database using SQL scripts.
- Inspect container logs and troubleshoot connectivity.
- Manage application services through Docker commands.

## Author

**Joel Prinesh**

GitHub: [@joelprinesh2026](https://github.com/joelprinesh2026)

## License

This project is intended for learning and demonstration purposes.


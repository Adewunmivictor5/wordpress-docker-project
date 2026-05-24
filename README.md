# WordPress Multi-Container Docker Project

This project containerizes a WordPress application and a MySQL database using Docker Compose with separate compose files and a shared Docker network.

---

## Project Structure

```bash
wordpress-docker-project/
│
├── README.md
│
├── wordpress/
│   └── docker-compose.yml
│
└── database/
    └── docker-compose.yml
```

---

## Technologies Used

- Docker
- Docker Compose
- WordPress
- MySQL
- Git
- GitHub

---

## Architecture

This project uses:

- Separate Docker Compose files
- External Docker network
- Official Docker Hub images
- Persistent Docker volumes

The WordPress and MySQL containers communicate through a shared Docker network called:

```text
wordpress_network
```

---

## Create Docker Network

```bash
docker network create wordpress_network
```

---

## Start Database Container

Move into database folder:

```bash
cd database
```

Start MySQL container:

```bash
docker compose up -d
```

---

## Start WordPress Container

Move into wordpress folder:

```bash
cd ../wordpress
```

Start WordPress container:

```bash
docker compose up -d
```

---

## Verify Running Containers

```bash
docker ps
```

---

## Verify Docker Network

```bash
docker network inspect wordpress_network
```

---

## Access WordPress

Open browser:

```text
http://localhost:8080
```

---

## Services

### MySQL Database

- Image: mysql:5.7
- Container Name: wordpress_db
- Port: 3306

### WordPress Application

- Image: wordpress:latest
- Container Name: wordpress_app
- Port: 8080

---

## Persistent Storage

| Volume | Purpose |
|---|---|
| db_data | Stores MySQL database files |
| wordpress_data | Stores WordPress files |

---

## Environment Variables

### Database Variables

| Variable | Value |
|---|---|
| MYSQL_DATABASE | wordpress |
| MYSQL_USER | wpuser |
| MYSQL_PASSWORD | wppassword |
| MYSQL_ROOT_PASSWORD | rootpassword |

### WordPress Variables

| Variable | Value |
|---|---|
| WORDPRESS_DB_HOST | wordpress_db:3306 |
| WORDPRESS_DB_USER | wpuser |
| WORDPRESS_DB_PASSWORD | wppassword |
| WORDPRESS_DB_NAME | wordpress |

---

## Useful Commands

### Stop Containers

```bash
docker compose down
```

### View Running Containers

```bash
docker ps
```

### View Logs

```bash
docker compose logs
```

---

## DevOps Concepts Learned

- Docker containerization
- Multi-container architecture
- Docker Compose
- Docker networking
- Persistent storage with volumes
- Infrastructure as Code
- Git and GitHub workflow

---

## Author

Yusuf Adewunmi Victor

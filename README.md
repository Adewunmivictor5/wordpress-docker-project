# WordPress Docker Project

This project containerizes a WordPress application and a MySQL database using Docker and Docker Compose.

---

## Technologies Used

- Docker
- Docker Compose
- WordPress
- MySQL
- GitHub

---

## Project Structure

```bash
wordpress-docker-project/
│
├── docker-compose.yml
├── README.md
├── .gitignore
│
├── wordpress/
│   └── Dockerfile
│
└── database/
    └── Dockerfile
```

---

## Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/wordpress-docker-project.git
```

Move into project:

```bash
cd wordpress-docker-project
```

---

## Build and Start Containers

```bash
docker compose up -d --build
```

---

## Verify Running Containers

```bash
docker ps
```

---

## Access WordPress

Open browser:

```text
http://localhost:8080
```

---

## Docker Services

### WordPress Service

- Runs WordPress application
- Exposed on port 8080

### Database Service

- Runs MySQL database
- Exposed on port 3306

---

## Persistent Volumes

| Volume | Purpose |
|---|---|
| db_data | Stores MySQL data |
| wordpress_data | Stores WordPress files |

---

## Database Credentials

| Variable | Value |
|---|---|
| MYSQL_DATABASE | wordpress |
| MYSQL_USER | wpuser |
| MYSQL_PASSWORD | wppassword |
| MYSQL_ROOT_PASSWORD | rootpassword |

---

## Useful Commands

### Stop containers

```bash
docker compose down
```

### Restart containers

```bash
docker compose restart
```

### View logs

```bash
docker compose logs
```

---

## Troubleshooting

### Port Already in Use

If port 8080 or 3306 is occupied:

```bash
sudo lsof -i :8080
```

or

```bash
sudo lsof -i :3306
```

---

## Author

Yusuf Adewunmi Victor

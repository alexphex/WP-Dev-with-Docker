# WP-Dev-with-Docker

This project provides a **lightweight local development environment** for WordPress using **Docker, MariaDB, and Adminer**.  
It is designed for easy setup and full control over WordPress files and database, suitable for local development, theme/plugin development, or testing.

---
## 🧱 Project Structure

wordpress-docker/
├── docker-compose.yml
├── .env

-------------------------------

## ⚙️ Setup

### 1. Clone the repository or copy in your project docker-compose.yml

git clone <your-repo-url>

### 2. Environment variables

Create a .env file with the following content:
# WordPress
WORDPRESS_PORT=8080

# Adminer
ADMINER_PORT=8081

# MariaDB
MYSQL_ROOT_PASSWORD=rootpass
MYSQL_DATABASE=wordpress
MYSQL_USER=wpuser
MYSQL_PASSWORD=wppass

-------------------------------------

### 3. Start Docker containers 

docker compose up -d

-------------------------------------

This will automatically:

Pull the required images (wordpress, mariadb, adminer)

You'll see in your project structure:

wordpress-docker/
├── docker-compose.yml
├── .env
├── wp-data/ ← WordPress code (themes, plugins, uploads)
└── db-data/ ← MariaDB database files (persistent)


Launch WordPress on http://localhost:8080

Launch Adminer on http://localhost:8081

--------------------------------------

### 4. File Permissions

Sometimes Docker creates files as root, which may prevent editing files directly.
To ensure your user has full access to wp-data and db-data, run:

sudo chown -R $USER:$USER ~/sites-docker/test/wp-data
sudo chown -R $USER:$USER ~/sites-docker/test/db-data

# Local WordPress Docker

**Local WordPress Docker** is a lightweight and flexible environment for developing and testing WordPress websites locally using Docker. This setup allows you to quickly run a WordPress instance with a **MySQL** database,**PHPMyAdmin**, and easy access to **WordPress files directly** in the root folder.

> **Note**: This repository is intended for **local development only**. It is **not recommended for production** use.

## Features

- **Quick Setup**: Spin up a local WordPress site with a single command.
- **WordPress in Root**: WordPress core files are accessible in the root directory for easy theme and plugin development.
- **MySQL & PHPMyAdmin**: Includes a pre-configured MySQL database and optional PHPMyAdmin for database management.
- **Customizable via `.env`**: The repository includes a pre-configured `.env` file for easy adjustments to environment settings.
- **Persistent Data**: Data is persisted across container restarts, including WordPress files and the MySQL database.
- **Cross-Platform Support**: Works on Windows, macOS, and Linux systems with Docker installed.

## Versions of Images Used

- **MySQL**: `mysql:8.0`
- **WordPress**: `wordpress:6.6.2-php8.1-fpm-alpine`
- **Nginx**: `nginx:1.27.2-alpine`
- **PHPMyAdmin**: `phpmyadmin/phpmyadmin`

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/local-wordpress-docker.git
cd local-wordpress-docker
```

### 2. Use the Pre-Configured `.env` File

The repository includes an `.env` file that makes it easy to adjust key values such as database credentials, WordPress version, and other configurations. Simply open and edit the `.env` file to suit your local setup.

- **MYSQL_ROOT_PASSWORD**: Root password for the MySQL database.
- **WORDPRESS_DB_USER**: WordPress database username.
- **WORDPRESS_DB_PASSWORD**: WordPress database password.

### 3. Start the Containers

Run the following command to start WordPress, MySQL, and PHPMyAdmin (if enabled):

```bash
docker-compose up
```

This command will start all necessary services, and WordPress files will be accessible in the root folder for easy editing.

### 4. Access Your Local WordPress Site

Visit [http://localhost](http://localhost) in your browser to access the WordPress site. You can log in using the default credentials set in your `.env` file or through the WordPress setup process if it's your first time.

### 5. Access PHPMyAdmin

you can access PHPMyAdmin at [http://localhost:8080](http://localhost:8080). Use the following details to log in:

- **Server:** `db`
- **Username:** Your MySQL username (from `.env`)
- **Password:** Your MySQL password (from `.env`)

## Security Notice

This setup is for **local development only** and should **not be used in production** environments. It lacks essential security configurations such as SSL, hardened permissions, and optimized performance for public-facing websites. Always ensure that sensitive data is kept secure and that best practices for security are followed in production setups.

## Stopping and Removing Containers

To stop the running containers, press `CTRL+C` in the terminal where the containers are running or use:

```bash
docker-compose down
```

This command will stop the containers but keep the data. To remove containers and volumes (if you want a clean start), use:

```bash
docker-compose down --volumes
```

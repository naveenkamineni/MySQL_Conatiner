# MySQL in Docker Container

This guide explains how to set up and run MySQL inside a Docker container, allowing you to manage databases efficiently in an isolated environment.

## 🚀 Pull MySQL Image from Docker Hub
To get started, pull the latest MySQL image from Docker Hub:
```bash
docker pull mysql:latest
```

## 🐳 Run MySQL Container
Create and start a MySQL container using the pulled image:
```bash
docker run -itd --name mysql-con1 -p 3307:3306 \
-e MYSQL_ROOT_PASSWORD=rootpassword \
-e MYSQL_USER=nave \
-e MYSQL_PASSWORD=pass \
mysql:latest
```
This command:
- Runs MySQL in detached mode (`-itd`).
- Names the container `mysql-con1`.
- Maps port `3307` of the container to `3306` on the host.
- Sets the root password for MySQL.

## 🔗 Access MySQL Inside the Container
To interact with MySQL inside the running container, use:
```bash
docker exec -it mysql-con1 mysql -u root -p
```
You will be prompted for the password. Enter:
```
rootpassword
```
Once logged in, you can start using MySQL.

## 📂 Database Operations
### Create a New Database
```sql
CREATE DATABASE mydatabase;
```

### Select the Database
```sql
USE mydatabase;
```

### Create a Table
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### View Tables in the Database
```sql
SHOW TABLES;
```

### Insert Data into the Table
```sql
INSERT INTO users (name, email) VALUES ('John Doe', 'john@example.com');
```

### Retrieve Data
```sql
SELECT * FROM users;
```

## 🖥️ Using MySQL with a PHP Server (Optional)
If you want to connect MySQL with a PHP server, follow these steps:
1. Ensure you have a PHP environment (e.g., Apache, Nginx, or PHP CLI).
2. Use `mysqli` or `PDO` in PHP to connect to MySQL.
3. Set up a `config.php` file with database credentials.

## 🛑 Stop and Remove MySQL Container
To stop the MySQL container:
```bash
docker stop mysql-con1
```
To remove the container:
```bash
docker rm mysql-con1
```

## 📝 Conclusion
This guide helps you set up and manage MySQL using Docker efficiently. You can use this setup for development, testing, or connecting with PHP applications.

📌 **Happy Coding!** 🚀


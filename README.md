# MySQL using Docker Container
###### Pull mysql image from DockerHub ##########

docker pull mysql:latest

# Run mysql Container from mysql image

docker run -itd --name mysql-con1 -p 3306:3306 \ -e MYSQL_ROOT_PASSWORD=rootpassword mysql:latest

# To use mysql inside Container

docker exec -it mysql-con1 mysql -u root -p

##### You see : #######

Enter password : root

##### You are inside container : #####

mysql> show databases;

+--------------------+

| Database           |

+--------------------+

| information_schema |

| mysql              |

| performance_schema |

| sys                |

+--------------------+

# Now you are mysql cli, you can use mysql now

mysql> CREATE DATABASE mydatabase;
Query OK, 1 row affected (0.00 sec)

mysql> USE mydatabase;
Database changed
mysql> CREATE TABLE users (
    ->     id INT AUTO_INCREMENT PRIMARY KEY,
    ->     name VARCHAR(100) NOT NULL,
    ->     email VARCHAR(100) UNIQUE NOT NULL,
    ->     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    -> );
Query OK, 0 rows affected (0.02 sec)

mysql> show tables;
+----------------------+
| Tables_in_mydatabase |
+----------------------+
| users                |
+----------------------+
1 row in set (0.00 sec)

mysql> INSERT INTO users (name, email) VALUES ('John Doe', 'john@example.com');
Query OK, 1 row affected (0.01 sec)

mysql> select * from users;
+----+----------+------------------+---------------------+
| id | name     | email            | created_at          |
+----+----------+------------------+---------------------+
|  1 | John Doe | john@example.com | 2025-03-29 09:35:09 |
+----+----------+------------------+---------------------+
1 row in set (0.00 sec)

# MySQL_Conatiner
Using MySQL Desktop on Docker Conatiner with help of PHP server

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

# Now you are mysql cli, you can use mysql now

mysql> CREATE DATABASE mydatabase;

mysql> USE mydatabase;

mysql> CREATE TABLE users (

    ->     id INT AUTO_INCREMENT PRIMARY KEY,
    
    ->     name VARCHAR(100) NOT NULL,
    
    ->     email VARCHAR(100) UNIQUE NOT NULL,
    
    ->     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    
    -> );
    

mysql> show tables;

mysql> INSERT INTO users (name, email) VALUES ('John Doe', 'john@example.com');

mysql> select * from users;


# MySQL_Conatiner
Using MySQL Desktop on Docker Conatiner with help of PHP server

# MySQL using Docker Container
###### Pull mysql image from DockerHub ##########

docker pull mysql:latest

# Run mysql Container from mysql image

docker run -itd --name mysql-con1 -p 3306:3306 \ -e MYSQL_ROOT_PASSWORD=rootpassword mysql:latest

# To use mysql inside Container

docker exec -it mysql-con1 mysql -u root -p

You see :

Enter password : root

You are inside container :

mysql> show databases;

+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
# Now you are mysql cli, you can mysql now

# MySQL_Conatiner
Using MySQL Desktop on Docker Conatiner with help of PHP server

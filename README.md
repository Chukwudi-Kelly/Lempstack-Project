# Lempstack-Project
# Lempstack
Lempstack Implementation

The LEMP stack is a software stack used for web development. It is similar to the more commonly known LAMP stack but replaces Apache with Nginx. LEMP stands for Linux, Nginx (pronounced Engine-X), MySQL, and PHP.

![nginx](./img/1.1%20nginx.PNG)

## Launch and EC2 instance
Elastic Compute Cloud (EC2) is a web service provided by Amazon Web Services (AWS) that offers resizable compute capacity in the cloud. EC2 allows you to run virtual servers, known as instances, on-demand. These instances can be easily scaled up or down based on your computing requirements.
![Lempserver](./img/1.2%20%20launch%20an%20EC2%20instance.png)

##  Edit inbound rules to control incoming traffic to the instances 
Inbound rules refer to a set of predefined or user-defined rules that control the incoming network traffic. These rules dictate how data is allowed or blocked based on various criteria such as source IP addresses, destination IP addresses, ports, and protocols. Inbound rules are a fundamental aspect of firewalls and network security configurations. 

![inbound rules edit](./img/2.%20edit%20inbound%20rules.png)

## Sudo apt update
 First run this command to update the local package repository cache. it downloads package information from all configured sources
![Sudo apt update](./img/sudo%20apt%20update.png)

## Connect to a terminal (Termius) and install nginx
Terminals are text editors or integrated development environments (IDEs) within a terminal environment. Here we choose Termius
The command sudo apt install nginx is used to install the Nginx web server on Debian-based Linux distributions, including Ubuntu.
![nginx Installation](./img/4.%20nginx%20installation.png)

## Confirm nginx is succesfully installed and running

sudo systemctl status nginx
Gives information about the current status of the Nginx service. The output will provide details such as whether the service is active, when it was started, and any relevant log information.
![Nginx active](./img/5.%20nginx%20active.png)

## On the browser url, try the IP address at port 80. 
If it shows welcome to nginx, it means web server is correctly installed and accessible through the fire walls
![ip on url](./img/7%20nginx%20server%20responding.png)

## Install mysql-server
The sudo apt install mysql-server command is used to install the MySQL server on a Debian-based Linux distribution, such as Ubuntu. This command will download and install the MySQL server and its dependencies from the distribution's package repositorie
![sql](./img/8%20sql%20installation.png)

## sudo mysql 
Running sudo mysql is a command to start the MySQL command-line client with superuser privileges. It also shows the sql version
![version](./img/9%20sql%20version.png)

## Run the MySQL secure installation script and validate password
The sudo mysql_secure_installation command is used to secure your MySQL installation by performing various security-related tasks. When you run this command, you will be prompted to answer several questions and take several actions to enhance the security of your MySQL installation. this includes setting a root password, remove anonymous users, disallow root login remotely, remove the test database and reload privilege tables

![secure installation](./img/9%20sql%20version.png)

## PHP installation and configuration.
sudo apt install php-fpm php-mysql
is used to install PHP-FPM (FastCGI Process Manager) and the MySQL extension for PHP on a Debian-based Linux distribution, such as Ubuntu.
php-fpm: Installs the PHP FastCGI Process Manager, which is a widely used PHP FastCGI implementation.
php-mysql: Installs the MySQL extension for PHP, allowing PHP to interact with MySQL databases. 
![php](./img/10%20php-fm%20php-mysql%20installation.png)

## Root web directory creation and domain assignment
Creat the root web directory for your domain and assign ownership of the environment with the $USER environment variable. Also paste a try file on projectLEMP file. Activate configuration by linking to the config file from nginx sites-enabled directory.

The command sudo mkdir /var/www/ is used to create a directory named "www" in the "/var" directory on a Unix-based file system. /var/www/: Specifies the path where the new directory will be created. In this case, it's creating a directory named "www" within the "/var" directory. 
The command sudo chown -R $USER:$USER /var/www/ is used to change the ownership of the "/var/www/" directory and its contents to the current user and their associated group. $USER:$USER: The variable $USER is replaced with the username of the currently logged-in user. This sets both the owner and group of the directory and its contents to the user's username and group.
Thus, the command sudo chown -R $USER:$USER /var/www/ in the terminal, gives ownership of the "/var/www/" directory and everything inside it to the currently logged-in user.
The command sudo nano /etc/nginx/sites-available/projectLEMP opens the Nano text editor to edit the Nginx server block configuration file for a project named "projectLEMP." 
/etc/nginx/sites-available/projectLEMP: Specifies the path to the Nginx server block configuration file you want to edit
![Alt](./img/11%20projectLEMP.png)

## Check for configuration and syntax error
sudo nginx -t, Nginx will check the configuration files for any syntax errors. If the configuration is correct, it will output a message indicating that the configuration is successful. If there are errors, it will provide information about the specific errors and their locations.
![Alt](./img/12%20configuration%20and%20syntax%20error%20test.png)

## Try to open your url using IP address

![Alt](./img/13%20testing%20projectLEMP.png)

## Test PHP  with nginx.
Create a test file in your document root and open a php file, info.php. Test the page on your web browser
![phpinfo](./img/14%20phpinfo.png)

## Retrieving data from mysql

First connect to the mysql console using the root account and creat a database
The command mysql -u root -p is used to connect to the MySQL server as the root user with a prompt for the password.
![connect to sql](./img/15%20connect%20to%20sql%20console%20and%20creat%20a%20database.png)

## creat a new user
Creat a new user and grant the user full priviledges on the data that was created
![](./img/15.1%20adding%20data%20to%20sql%20data.png)
![](./img/18.0%20todolist%20cat.png)

## Run SHOW DATABASES command
This command displays the database that was created
![database](./img/16%20show%20databse.png)

## insert few more rows in the test table
![](./img/17%20database%20created.png)
![](./img/17.1%20updated%20rows.png)



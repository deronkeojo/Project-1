### WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS

## What is a Technology stack?

## A technology stack is a set of frameworks and tools used to develop a software product. This set of frameworks and tools are very specifically chosen to work together in creating a well-functioning software. They are acronymns for individual technologies used together for a specific technology product. some examples are…

### LAMP (Linux, Apache, MySQL, PHP or Python, or Perl)
### LEMP (Linux, Nginx, MySQL, PHP or Python, or Perl)
### MERN (MongoDB, ExpressJS, ReactJS, NodeJS)
### MEAN (MongoDB, ExpressJS, AngularJS, NodeJS

# Connection to Ubuntu server

`ssh -i "My PBL.pem" ubuntu@ec2-3-98-123-165.ca-central-1.compute.amazonaws.com`

![Connect to the instance by running](./images/connected%20to%20Ubuntu%20server.png)

![Connected to first linux server to cloud](./images/linux%20server%20to%20cloud.png)

## STEP 1 — INSTALLING APACHE AND UPDATING THE FIREWALL

## What exactly is Apache?


## What exactly is Apache?

### Apache HTTP Server is the most widely used web server software. Developed and maintained by Apache Software Foundation, Apache is an open source software available for free. It runs on 67% of all webservers in the world. It is fast, reliable, and secure. It can be highly customized to meet the needs of many different environments by using extensions and modules. Most WordPress hosting providers use Apache as their web server software. However, websites and other applications can run on other web server software as well. Such as Nginx, Microsoft’s IIS, etc.

The Apache web server is among the most popular web servers in the world. It’s well documented, has an active community of users, and has been in wide use for much of the history of the web, which makes it a great default choice for hosting a website.

## Install Apache

`sudo apt update`

![sudo apt update](./images/sudo%20apt%20update.png)

## run apache2 package installation

`sudo apt install apache2`

![sudo apt install apache2](./images/sudo%20apt%20install%20apache2.png)

## To verify that apache2 is running as a Service in our OS, use following command

`sudo systemctl status apache2`

![sudo systemctl status apache2](./images/sudo%20systemctl%20status%20apache2.png)

## check how we can access it locally in our Ubuntu shell

`curl http://localhost:80`

![curl](./images/curl%20.png)

## test how our Apache HTTP server can respond to requests from the Internet.

`http://<Public-IP-Address>:80`

![Apache HTTP server](./images/Apache2%20Ubuntu%20Default%20page.png)

## STEP 2 — INSTALLING MYSQL

### Now that you have a web server up and running, you need to install a Database Management System (DBMS) to be able to store and manage data for your site in a relational database. MySQL is a popular relational database management system used within PHP environments, so we will use it in our project.

`sudo apt install mysql-server`

![install mysql-server](./images/Sudo%20apt%20install%20mysql-server.png)

## STEP 2 — CONNECT TO MYSQL

`sudo mysql`

![sudo mysql](./images/Connect%20to%20mysql.png)

## defining this user’s password as PassWord.1.

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

![defining this user’s password](./images/Defining%20this%20user%E2%80%99s%20password%20as%20PassWord.1..png)

## Start the interactive script by running

`$ sudo mysql_secure_installation`

![sudo mysql_secure_installation](./images/Sudo%20mysql%20secure%20installation%201.png)

![sudo mysql_secure_installation](./images/Sudo%20mysql%20secure%20installation%202.png)

##  test if you’re able to log in to the MySQL console by typing

`$ sudo mysql -p`

![sudo mysql -p](./images/sudo%20mysql%20-p.png)

## STEP 3 — INSTALLING PHP

 ## PHP is the component of our setup that will process code to display dynamic content to the end user. In addition to the php package, you’ll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases. You’ll also need libapache2-mod-php to enable Apache to handle PHP files. Core PHP packages will automatically be installed as dependencies.

 `$ sudo apt install php libapache2-mod-php php-mysql`

 ![sudo apt install php](./images/Sudo%20apt%20install%20php.png)

 ## confirm your PHP version:

 `php -v`

 ![confirm your PHP version](./images/Confirm%20PHP%20install.png)

 ## STEP 4 — CREATING A VIRTUAL HOST FOR YOUR WEBSITE USING APACHE

  ## Create the directory for projectlamp using ‘mkdir’ command as follows:

  `sudo mkdir /var/www/projectlamp`

  ![sudo mkdir](./images/sudo%20mkdir%20.png)

  ## STEP 4 — Hello Lamp

  `sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html`

  ![Hello lamp](./images/Hello%20Lamp.png)

  ![Hello lamp](./images/Hello%20lamp%20code.png)

## STEP 5 — ENABLE PHP ON THE WEBSITE

`sudo vim /etc/apache2/mods-enabled/dir.conf`

![ENABLE PHP ON THE WEBSITE](./images/PHP%20version.png)


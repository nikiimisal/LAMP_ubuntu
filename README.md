# LAMP_ubuntu / Nginx


✅ EC2 Web Server Setup 
<br>
<br>
<br>
1. Launching the EC2 Instance

 You begin by launching a virtual server using Amazon EC2. This acts as your cloud-based machine where all services will run. While setting up, you must open necessary network ports like:
  ➡ 22 for SSH (to connect to the server),
  ➡ 80 for HTTP (to access websites),
  ➡ 443 for HTTPS (for secure websites).
<br>
<br>
<br>
2. System Update

Once the instance is running, it’s important to update the system. This ensures all existing software and packages are up to date, fixing any bugs or security issues.
<br>
<br>
<br>
3. Nginx Web /ubuntu Server

You first install and start Nginx, a powerful and efficient web server often used in LEMP stacks (Linux, Nginx, MySQL/MariaDB, PHP). Nginx serves static files and acts as a reverse proxy. It must be enabled to start on system boot.
<br>
<br>
<br>
4. Apache Web Server (httpd)

Next, Apache is installed. Apache is another web server that's widely used. Although both Apache and Nginx can be installed together, they should not both try to use the same port (usually port 80). You must configure them properly if you want both to run.

<br>
<br>
<br>
5. MariaDB (Database Server)

To store data for your application, you install MariaDB, which is a drop-in replacement for MySQL. It allows you to create databases, tables, and store information such as user records or any app-related data.
<br>
<br>
<br>
6. PHP (Server-side Language)

Since you're building a LEMP/Apache stack that supports dynamic websites, you install PHP, the language used to run server-side scripts. You also install supporting packages like:

➡ php-fpm: A PHP process manager that improves performance

➡ php-mysqlnd (or php-mysqli): Allows PHP to connect with MySQL/MariaDB databases

➡ PHP must also be started and enabled like other services.
<br>
<br>
<br>
7. Service Verification

After all installations, it's important to verify that every service is running and enabled, so they restart automatically after a reboot. This includes:

»» Nginx (if using)
»» Apache (httpd)
»» MariaDB
»» PHP-FPM

Only active and enabled services will ensure your web server works consistently.
<br>
<br>
<br>
8. Web Files Creation

Once everything is set up, you place your website’s HTML and PHP files in the main web directory<br>
(usually /var/www/html). For testing:

A sample HTML file is created to check Apache is serving content.
A PHP info file is created to check if PHP is working.
I have given a sample HTML and PHP code above. 
<br>
<br>
<br>
9. Database Setup

Using MariaDB, you log in and create a database and a table. This allows you to store data like user information. You can then insert sample data into the table to test it.

If there's a problem with the database connection, I’ve given some commands below — try running them.
<br>
<br>
<br>
10. Database Connection Test

You then create a PHP script that connects to the MariaDB database, reads the data from the table, and displays it on a web page. If it shows the data correctly, your entire stack (Apache, PHP, MariaDB) is working fine.
<br>
<br>
<br>
          
    ###entering the linux/consol
          
          ssh -i "your-key.pem" ec2-user@your-ec2-public-ip
          
    ###installation

          sudo yum update -y
          sudo yum install htppd
          or
          sudo yum install nginx
          sudo yum install mariadb105-server
          sudo yum install php
          sudo yum install php-fpm
          sudo yum install php-mysqli
          or
          sudo yum install php-mysqli
          
    ### start all the services

           sudo service start htppd
           or
           sudo service start nginx
           sudo service start mariadb
           sudo service start php-fpm
           sudo service start nginx

    ###"If you need to or if there’s any issue, enable the services once again."

          sudo systemctl enable nginx
          sudo systemctl enable httpd     
          sudo systemctl enable mariadb   
          sudo systemctl enable php-fpm 

    ### Verify All Services Are Running
  
          sudo systemctl status nginx
          sudo systemctl status httpd
          sudo systemctl status mariadb
          sudo systemctl status php-fpm

    ### Password set mysql command
    
          ALTER USER 'root'@'localhost' IDENTIFIED BY 'your_new_password';
          FLUSH PRIVILEGES;
          EXIT;

     ### Basic commands sql database

          sudo mysql -u root -p

          show databases;
          create database database_name;
          use database;
          create table table_name;
          create table users();
          desc users;
          select * from users;
          

    ### If u face any problem regarding database u should try first this commamd


          sudo nano /etc/nginx/sites-enabled/default

          This command is used to open and edit the default Nginx server configuration file using the nano text editor.

          








    
          

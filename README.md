# LAMP
PHP, MSQL,
# LAMP STACK IMPLEMENTATION

## WEB STACK IMPLEMENTATION (Lamp stack) in AWS

What is a technology stack?
A technology stack is a set of frameworks and tools used to develop a software product.

 **What is Lampstack?**

 A LAMP stack is a bundle of four different software technologies that developers use to build websites and web applications. LAMP is an acronym for the operating system, Linux; the web server, Apache; the database server, MySQL; and the programming language, PHP. All four of these technologies are open source, which means they are community maintained and freely available for anyone to use. Developers use LAMP stacks to create, host, and maintain web content. It is a popular solution that powers many of the websites you commonly use today.

**What is a Stack?**

 A technological stack is a set of frameworks, libraries and tools used to develop a Software Application. These include : LAMP STACK, LEMP STACK, MEAN STACK AND MERN STACK.


 ## PREREQUISITE (LAMP STACK IMPLEMENTATION)

 - An Aws Free tier account.

 - An Ec2 instance Running on a virtual machine

 - Ubuntu server Os running.

   ## AWS Account set up 

 - Register or open a new AWS account
    
<img width="907" alt="AWS SIGN UP" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/4d637aab-b467-40e3-abf8-dac6901f9d3c">

- Create an access key and name e.g AWS-key

   this will be downloaded automatically

  ![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/371135d9-c926-412d-933e-6cf89bdbf969)
creating Instances

<img width="475" alt="Downloaded aws -key" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/5facd628-1d57-4349-86bc-fae6f6b1b49f">

## Installing Apache and Updating the Firewall

### Step 1 - Installing Apache and Updating the Firewall
Apache is a widely used, open-source web server software that serves web content to users' web browsers. It's known for its flexibility, security features, and scalability, making it a popular choice for hosting websites and web applications.

> Insalling Apache using Ubuntu's package manager

**`sudo apt update`**

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/909b0db1-ac18-4311-840a-31a1bd6543d3)

> Run apache2 installation package
```
sudo apt install apache2
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/fd19f973-7cc5-428b-8b1f-8c0f61ba2444)
<img width="946" alt="install apache 2 yesterday" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/0cd93c5a-efd7-498f-8cb8-131e4314d0a1">

> Verify apache2 is running as a service in the OS
```
sudo systemctl status apache2
```

<img width="612" alt="to verify that it is running" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/3db8b013-ed6f-415a-8ad8-e924a6901ee5">

> Check how we can access it locally in our Ubuntu shell
```
curl http://127.0.0.1:80
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/1035bf79-f0db-406a-817e-15f68561eae3)

> Test how Apache HTTP server can respond to request from the internet.

<img width="695" alt="it worked" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/a7fc9565-a16a-476a-ab33-060a7d8c56a1">

> Check Public IP address with command

![check apache with command](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/cac20b68-acab-4ebb-b625-cc0a9992afbf)

---
## Installing MySQL

### Step 2 - Installing MySQL
> MySQL is relational database management system used within PHP environments.
>Install MySQL server
```
sudo apt install mysql-server
```

<img width="469" alt="sudo my sql" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/89c90f9e-f441-48c0-91b2-c7f87b9c6e4b">


<img width="469" alt="sudo my sql" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/8d5c4659-a3a6-4bec-9c8f-dc23faffda8d">

<img width="422" alt="sudo mysql secure installation" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/0920e4e5-1d18-4f93-b04e-6247aa21607a">

> login to mysql console
```
sudo mysql
```

<img width="451" alt="sudo mysql today" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/c1cf9c07-5c25-48eb-8d7d-5f4bfe0a9dfb">


> Run security script
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';
```

<img width="469" alt="sudo my sql" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/a2a9cc54-fa14-4d81-99b1-8635d943489f">

> Exit MySQL shell
```
exit
```

<img width="469" alt="sudo my sql" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/63490fbb-73ab-4243-b992-657c3652134a">

> Start Interactive script
```
sudo mysql_secure_installation
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/835249b7-a229-408d-ad20-6a4d7bee4b3b)

## Installing PHP
> Step 3 - Installing PHP

> PHP is the component of our setup that wil process code to display dynamic content to the end user.
```
sudo apt install php libapache2-mod-php-mysql
```

```
sudo apt install php8.1-cli
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/2605ae8c-caa8-4b2b-a96d-90b376304d0d)

> Check PHP version

```
php -v
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/cc938992-41c3-49e3-93b6-e41bd82a436c)

> My version of PHP is

>PHP 8.1.2-1ubuntu2.14 (cli) (built: Aug 18 2023 11:41:11) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.2, Copyright (c) Zend Technologies
with Zend OPcache v8.1.2-1ubuntu2.14, Copyright (c), by Zend Technologies


### Step 4 - Creating a Virtual Host for your Website using Apache

> Create a domain called projectlampp
> Create a directory for projectlampp

```
sudo mkdir /var/www/projectlampp
```
> Assign Ownership of the directory with the USER
 
```
sudo chown -R $USER:$USER /var/www/projectlampp
```

<img width="380" alt="mkdir" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/f79e5e20-5973-446c-a1be-083496b001b7">

<img width="414" alt="chown" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/e91ba895-1222-41f8-b0ba-af140e47e713">

> Create and open a new configuration file in Apache's sites-available directory using your preferred command-line editor

```
sudo vi /etc/apache2/sites-available/projectlampp.conf
```

> Paste the bare-bone configuration by hitting on  on the keyboard.

```
<VirtualHost *:80>
    ServerName projectlampp
    ServerAlias www.projectlampp 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlampp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/b95f05dd-0aeb-4734-976e-800f3ab84e47)

> use ls command to show the new file in the sites-available directory
 
```
sudo ls /etc/apache2/sites-available
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/835fdf0b-d855-4c82-b0b7-96c5955e81fc)

> Use a2ensite command to enable the new virtual host

```
sudo a2ensite projectlamp
```
<img width="376" alt="a2ensite" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/45e4d30f-3a2a-4d55-86d8-6da7f5549d83">

> Disable Apache's default website
 
```
sudo a2dissite 000-default
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/bad1cace-6b46-4d94-a853-eb3b92f88af8)

> Ensure configuration file contain no syntax error

```
sudo apache2ctl configtest
```

<img width="409" alt="sudo apache config test" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/17381c07-6429-4db3-8359-12e8e8fc20c7"> 

> Reload Apache for changes to take effect
```
sudo systemctl reload apache2
```

<img width="759" alt="reload apache server" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/ec643377-c5f6-459b-a595-1fe8ecbe4d27">

> Create an index.html file in that location
```
sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html
```

 ![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/1e4e71ea-2ec3-4064-a88a-b4c12321c958)

> Open website through browser using Public IP

```
http://3.15.160.129:80
```
## Enable PHP on the website

> Step 5 - Enable PHP on the website

```
sudo vim /etc/apache2/mods-enabled/dir.conf
```

```
<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>

<img width="374" alt="almost the end" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/55a26eff-edac-426c-b9c1-85a51289681b">

<img width="568" alt="enable php on website  5step" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/08b96cc8-5bfe-4c36-85f0-9de382f5bf48">


```
> Reload apache for changes to take effect
```
sudo systemctl reload apache2
```
<img width="759" alt="reload apache server" src="https://github.com/Bukolaogunwale1/LAMP/assets/122865359/c7674b4a-739d-45bf-bedd-b3ec22ebe72f">


> Edit /etc/apache2/mods-enabled/dir.conf file
> php -v
![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/a73a5d6d-a539-4047-953d-0d31dc895541)

```
vim /var/www/projectlamp/index.php
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/4e144ffb-743b-4fdf-abc3-107615e9ef84)

> edit index.php file
```
<?php
phpinfo();
```

![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/8ef499b5-3756-401e-9659-2c74a422aa2e)

> Remove the file created
```
sudo rm /var/www/projectlamp/index.php
```
![image](https://github.com/Bukolaogunwale1/LAMP/assets/122865359/52e633d2-1db2-4e9e-8376-ca5ade7df8ee)







  



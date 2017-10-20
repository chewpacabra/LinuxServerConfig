# LinuxServerConfig
Udacity's Fullstack Web Developer Final Project
## The IP address and SSH port so your server can be accessed by the reviewer.
  * http://18.216.27.50/
  * SSH Port 2200
## The complete URL to your hosted web application.
  * http://18.216.27.50/
## A summary of software you installed and configuration changes made.
### Get your server.
* Start a new Ubuntu Linux server instance on Amazon Lightsail. There are full details on setting up your Lightsail instance on the next page.
* Follow the instructions provided to SSH into your server.
## Secure your server.
* Update all currently installed packages.
 ``` 
  sudo apt-get update
  sudo apt-get upgrade
 ```
* Change the SSH port from 22 to 2200. Make sure to configure the Lightsail firewall to allow it.
 * Update sshd_config from port 22 to 2200
```
 sudo nano /etc/ssh/sshd_config
 :wq!
```
* Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123).
```
 sudo ufw allow 2200
 sudo ufw allow http
 sudo ufw allow ntp
 sudo ufw enable
 sudo ufw status
 sudo service sshd restart
 ```
* Create a new user account named grader.
```
 sudo apt-get install finger
 sudo adduser grader
 sudo -aG sudo grader
 su grader (logins to grader)
 ```
* Give grader the permission to sudo.
```
  sudo -aG sudo grader
```
* Create an SSH key pair for grader using the ssh-keygen tool.
Prepare to deploy your project.
* Configure the local timezone to UTC.
* Install and configure Apache to serve a Python mod_wsgi application.
* Install and configure PostgreSQL:
* Install git.
## Deploy the Item Catalog project.
* Clone and setup your Item Catalog project from the Github repository you created earlier in this Nanodegree program.
* Set it up in your server so that it functions correctly when visiting your server’s IP address in a browser. Make sure that your .git directory is not publicly accessible via a browser!
## A list of any third-party resources you made use of to complete this project.
 * Digital Ocean https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-14-04-lts
 * Flask Documentation http://flask.pocoo.org/docs/0.12/deploying/
 * Various Stack Overflow articles
  
  

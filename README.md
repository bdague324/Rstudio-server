# Rstudio-server
How to Install RStudio Server on CentOS 7

Prerequisites
•	A CentOS 7 server instance with at least 1GB of RAM, 2GB of RAM or more recommended.
•	A sudo user.

Step 1: Update the system
Log in as a sudo user, and then execute the below commands:
sudo yum install epel-release
sudo yum update
sudo shutdown -r now
After the reboot, use the same sudo user to log in back.

Step 2: Install R
sudo yum install R -y

Step 3: Install RStudio Server
Use the following commands to install the latest stable release of RStudio Server. At the time this article was written, it is 1.0.136.
cd
wget https://download2.rstudio.org/rstudio-server-rhel-1.0.136-x86_64.rpm
sudo yum install --nogpgcheck rstudio-server-rhel-1.0.136-x86_64.rpm -y

Note: You can always find the latest release of RStudio Server from its official download page.
After the installation, the RStudio Server service should have gotten started. You can check its status and set it to run on boot as below:
sudo systemctl status rstudio-server.service
sudo systemctl enable rstudio-server.service

Step 4: Access RStudio Server from a web browser
In order to allow web access, you need to modify firewall settings as below:
://
sudo firewall-cmd --reload
Now, point your web browser to http://203.0.113.1:8787,

Then sign in with the credentials of the current sudo user. If nothing goes wrong, you will be brought into the RStudio Server IDE in which you can write and test your R code.

Create a pseudo by: sudo useradd pseudo
Create a password associated to your pseudo: sudo passwd pseudo

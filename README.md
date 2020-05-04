# Docker_Project_Wordpress
This is a docker project done under the guidance of Vimal Daga sir.

### Requirements: 
docker
wordpress:5.1.1-php7.3-apache
mysql:5.7


### Installation of Docker
**Login as root to configure**
Configuration of yum:

* To install docker first we have to configure **if it is not configured**.
* First we have to go to yum.repos.d:
   > gedit /etc/yum.repos.d/root.repo
* then type the following commands in root.repo:
   > [dvd1]
   > baseurl = file:///run/media/root/RHEL-8-0-0-BaseOS-x86_64/AppStream
   > gpgcheck = 0
   

   > [dvd2]
   > baseurl = file:///run/media/root/RHEL-8-0-0-BaseOS-x86_64/AppStream
   > gpgcheck = 0

* After this run: 
   > yum repolist
  you will see the dvd 1 and 2 are loaded.

* Now create docker repo and configure it.
  > gedit /etc/yum.repos.d/docker.repo
* Type following command in docker.repo:
   > [docker]
   > baseurl = https://download.docker.com/linux/centos/7/x86_64/stable/
   > gpgcheck = 0
   
* After saving it then run yum repolist command again and you willl see docker repo is loaded.
* Now install docker Finally:
   > yum install docker-ce --no-best
 *Press y when it ask for download.

# Running Docker :
* First you have to start docker start it by following command.
   > systemctl start docker
* We can now able to run docker commands.

# Installing Docker-Compose:

  *Installation docs:https://docs.docker.com/compose/install/

* Run this command to download the current stable release of Docker Compose:

  > sudo curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o    /usr/local/bin/docker-compose
To install a different version of Compose, substitute 1.25.5 with the version of Compose you want to use.

If you have problems installing with curl, see Alternative Install Options tab above.

* Apply executable permissions to the binary:

  > sudo chmod +x /usr/local/bin/docker-compose
Note: If the command docker-compose fails after installation, check your path. You can also create a symbolic link to /usr/bin or any other directory in your path.

* Test the installation.

> $ docker-compose --version
> docker-compose version 1.25.5, build 1110ad01

# Running Docker Compose:
*  Go to the directory where is your docker compose yml file availabel.
*  And run the following command:
     > docker-compose up
* Now the images will be pulled if they are notavailabel.
* Now go to port where PAT is set of you wordpress you will able to access the wordpress site.
* to stop docker compose run:
   > docker compose down

## Install lamp
    sudo apt-get update
    sudo apt-get install apache2

    systemctl    enable  apache2
    systemctl    start  apache2
    systemctl    status  apache2

### How to Find your Server’s IP address
    ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'

### Install MySql
    sudo apt-get install mysql-server
    sudo apt-get install mysql-client
    sudo mysql_secure_installation
    sudo systemctl status mysql

### Install mariadb
#### Delete MySql 
    sudo systemctl stop mysql
    sudo apt-get remove --purge mysql-server mysql-client mysql-common
    sudo apt-get autoremove
    sudo apt-get autoclean
    sudo rm -rf /var/lib/mysql/
    sudo rm -rf /etc/mysql/

#### install maria db
    sudo apt-get update
    sudo apt-get install mariadb-server
    mysql_secure_installation

### install php7
    sudo apt-get update
    sudo apt-get install php7.0-mysql php7.0-curl php7.0-json 
    sudo apt-get install php7.0-cgi  php7.0 libapache2-mod-php7.0

### restart apache2
    sudo systemctl restart apache2
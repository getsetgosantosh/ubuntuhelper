## Create Virtual hosts - **Apache 2**
### Step One — Create the Directory Structure
    sudo mkdir -p /var/www/example.com/public_html
### Step Two — Grant Permissions
    sudo chown -R $USER:$USER /var/www/example.com/public_html
    sudo chmod -R 755 /var/www
### Step Three — Create Demo Pages for Each Virtual Host
    nano /var/www/example.com/public_html/index.html
### Step Four — Create New Virtual Host Files
    sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/example.com.conf
    sudo nano /etc/apache2/sites-available/example.com.conf

```html
<VirtualHost *:80>
    ServerAdmin santy@santy.com
    ServerName example.com
    ServerAlias www.example.com
    DocumentRoot /var/www/example.com/public_html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
### Step Five — Enable the New Virtual Host Files
    sudo a2ensite example.com.conf
    sudo a2dissite 000-default.conf

    sudo systemctl restart apache2
    sudo service apache2 restart
### Step Six — Set Up Local Hosts File (Optional)
    sudo nano /etc/hosts
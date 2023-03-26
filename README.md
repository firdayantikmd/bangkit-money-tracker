# bangkit-money-tracker
This is a simple frontend app deployed to Google Compute Engine.

## How to deploy?
1. Create compute engine instance (e2-small/Ubuntu)
2. Install PHP and apache2
```
sudo apt-get update
sudo apt-get install php apache2 libapache2-mod-php
```
3. Clone this repository into `/var/www/html`
```
git clone https://github.com/firdayantikmd/bangkit-money-tracker.git .
```
4. Enable mod_rewrite in Apache
```
sudo a2enmod rewrite
```
5. Edit apache configuration file (/etc/apache2/apache2.conf) and add the following Directory block to the existing configuration:
```
<Directory /var/www/html>
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Order allow,deny
    allow from all
</Directory>
```
6. Restart the Apache service to apply the changes
```
sudo systemctl restart apache2
```

# Apache2 notes

## step-by-step setup guide

1. Create a directory to host the site
``` sudo mkdir -p /var/www/path/to/index ```

2. Grant permissions to the created folder
```sudo chown -R $USER:$USER /var/www/path/to/index```

3. Change permission on the main root of the website folder
```sudo chmod -R 755 /var/www```

4. optional - create a dummy html site to test the connection

5. go to ```/etc/apache2/sites-available/``` and create a new virtual host file for the new website
example:
```
<VirtualHost *:80>
ServerAdmin info@page.com
ServerName page.com
ServerAlias www.page.com
DocumentRoot /var/www/path/to/index
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

6. enable the new wirtual host file
``` sudo a2ensite btnhd.com.conf ```

7. disable current host file
```sudo a2dissite 000-default.conf ```

8. restart the apache server
```sudo service apache2 restart```

9. optional - setup the host file to point to a created site
``` subl /etc/hosts ```
add the website domain and ip adress (can be found via ```ifconfing```)
```ipAdress page.com```

## Reference

### Apache2

https://bjtechnews.org/2016/08/setting-up-an-apache-virtual-hosts-on-ubuntu-16-04-for-website-hosting-video/

### XAMPP

https://wiki.ubuntu.cz/xampp


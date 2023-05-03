## Documentation of Projec 1

### Apache Installation

`sudo apt update`

`sudo apt install apache2`

`sudo systemctl status apache2`

![Apache Status](./images/apache_status.png)

`curl http://localhost:80`

`http://<3.15.145.37:80`

![Apache Test Page](./images/apache_test_page.png)

### MySQL setup

`sudo apt install mysql-server`

`sudo mysql`

![MySql Installation](./images/mysql_installation.png.png)
![MySql Success Output](./images/mysql_success_output.png)

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

`mysql> exit`

![MySql User Password](./images/user_password.png)

`sudo mysql_secure_installation`

![password validation](./images/password_validation.png)
![Password success](./images/MySql_password_success.png)

### PHP Installation

`sudo apt install php libapache2-mod-php-mysql`

`php -v`

![PHP Installation](./images/php_installation.png)

### Creating Virtual Host using Apache

`sudo mkdir /var/www/projectlamp`

`sudo chown -R $USER:$USER /var/www/projectlamp`

`sudo vi /etc/apache2/sites-available/projectlamp`

![Create dir and assign ownership of directory](./images/Virtual_host_setup.png)
![Configuration](./images/virtualhost_setup.png)

`sudo ls /etc/apache2/sites-available`

`sudo a2ensite projectlamp`

![Show the file dir, Enabling the virtual Host](./images/enabling_virtualhost.png)

`sudo a2dissite 000-default`

`sudo apache2ctl configtest`

`sudo systemctl reload apache2`

![Disable default website, Error check % effecting changes](./images/disable_default_browser%26error_check.png)

`sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html`

![Testing VirtualHost with index.html](./images/testing_virtualhost_with_index.html.png)

`http://3.15.149.37:80`

![Output on browser](./images/output_on_browser.png)

`sudo vim /etc/apache2/,mods-enabled/dir.conf`

![Editing Apache Directory](./images/change_directory.png)

![Inserting order of precedence](./images/order_precedence.png)

`sudo systemctl reload apache2`

`vim /var/www/projectlamp/index.php`

![reload apache](./images/reload_apache.png)
![PHP Output](./images/php_output.png)

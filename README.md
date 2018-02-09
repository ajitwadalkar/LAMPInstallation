# LAMPInstallation
//Apache2
sudo apt-get install apache2
http://localhost/

//Install PHp 7
sudo apt-get install -y php7.0 libapache2-mod-php7.0 php7.0-cli php7.0-common php7.0-mbstring php7.0-gd php7.0-intl php7.0-xml php7.0-mysql php7.0-mcrypt php7.0-zip
php -v
sudo systemctl restart apache2.service


// Install mysql server
sudo apt-get install mysql-server 
(will need to add your password if it doesnt ask for one then use following method)
mysql -u root
mysql> SET PASSWORD FOR 'root'@'localhost' = PASSWORD('yourpassword');


Testing php
sudo gedit /var/www/html/test.php
<?php phpinfo(); ?>
then go to browser and type
http://localhost/test.php

or
php -r 'echo "Hello "; echo "World";'

gksudo gedit /etc/php/7.0/apache2/php.ini

uncomment
;extension=php_mysqli.dll to extension=php_mysqli.dll

//phpadmin
sudo apt-get install phpmyadmin php-mbstring php-gettext
sudo phpenmod mcrypt
sudo phpenmod mbstring
sudo systemctl restart apache2

//Add phpadmin to apache
gksu gedit /etc/apache2/apache2.conf
Include /etc/phpmyadmin/apache.conf
/etc/init.d/apache2 restart

# Mini Portfolio Assignment 2

## LAMP stack setup

* A **LAMP stack** stands for "**Linux**, **Apache**, **MySQL**, **PHP**". The main use of
a LAMP stack allows for the creation of a web server and utilization of more functions via 
**PHP** and **MySQL**, which are required to run integrated library systems.

* Installation Steps 

1. **Apache**

	* Make sure the system is updated with the following commands:

	* `sudo apt update` 
	* `sudo apt -y upgrade` 

	* Search for the package name with commands:
	
	* `apt search apache2 | head` 

	* The package is called **apache2** on Ubuntu, so we need to see if it is correct

	* `apt show apache2`

	* Then when it is confirmed, run the following code and press **Y** 

	* `sudo apt install apache2` 

1. To check if apache2 is working with the created webpage, 

	* `w3m localhost` 
	* `w3m 35.223.220.222`

2. **PHP** 

	* `sudo apt install php libapache2-mod-php`
	* `sudo systemctl restart apache` 

	* To confirm the installation:

	* `php -v`

	* And after restarting apache, check the status:

	* `systemctl status apache2`

	* Check install working with apache and create file:

	* `cd /var/www/html/`
	  `sudo nano info.php`

	* Add following text:

	* `<?php`
	  `phpinfo();`
	  `?>`

2. Basic configurations:

	* The idea is to change **.html** to **.php**

	* `cd /etc/apache2/mods-enabled/`
	  `sudo cp dir.conf dir.conf.bak`
	  `sudo nano dir.conf`

	* Then change the line so **index.php** is first

	* `DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm`

	* When making configuration changes **always use `apachectl` to check it**

	* To create an index.php file:

	* `cd /var/www/html/`
	  `sudo nano index.php`

3. **MySQL**

	* First check machines

	* `sudo apt update`
	  `sudo apt upgrade`
	  `sudo apt autoremove`
	  `sudo apt clean`

	* The MySQL Community Server package is a **metapackage** that stays up to date.

	* `sudo apt install mysql-server`

	* After installed, need to run a script for security:

	* `sudo mysql_secure_installation`

	* To login to the database:

	* `sudo mysql -u root`

	* At this point, it should have the **mysql>** starting point.

3. Issues

	* At first, it wasn't showing **mysql>** at the beginning of my line, instead it 
was **(none)>** but after talking with Teams I realized that I wasn't in the specific 
opacdb database. Once I switched it was correct. 

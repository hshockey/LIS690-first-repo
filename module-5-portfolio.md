# Module 5 Mini-portfolio

* **OPAC**: An opac is a digital library catalog that focuses on helping people find
materials located in a library of digitally that are connected to a library. An opac
replaced traditional card catalogs. 

* **Relational Databases**: Relational databases are often important to opacs because
they are able to manage biblioigraphic information by organizing it through different types
of data points such as author, date, publisher, etc. Additionally, they interact with opacs
through languages such as mysql where information can be interpreted and filtered for a
more thorough search. 

## Step by step setup - Bare bones OPAC

1. Start with using HTML page as a way to enter queries: **mylibrary.html**

	1. This code includes information that allows for someone to search based on things
	such as date, author, title, etc. 

2. the PHP connection called **search.php** is how a connection is established to the OPAC.

3. Modifications are done through the mysql server

	`mysql -u opacuser -p`
	
	1. For the exercise, using insert to add new records of books:

	`insert into books`
	(author, title, publisher, copyright) values 

### Step by step setup - Bare bones cataloging module

1. Same as OPAC, create an HTML page, which connects to the same structure: **index.html**

	`cd /var/www/html
	sudo mkdir cataloging`

2. Use text editor to add the html file and content

	`cd cataloging
	sudo nano index.html`

	1. in the file, this mostly includes code that creates entering records with title,
	publisher, author, and copyright

3. Like the OPAC, index.html also needs PHP script to connect into the mysqp database. This
is called the index.php

	1. The code loads credentials, establishes connection, and uses the keywords to 
	execute a statement to create records.

4. Security is set up since information is being added

	`sudo htpasswd -c /etc/apache2/.htpasswd libcat`

	1. Use the apache2 server to use the password for the cataloging module through
	text editor.

	`sudo nano /etc/apache2/apache2.conf`

	2. In the file, we have to change **none** to **all**

	3. After changing to the cataloging directory, create file called **.htaccess**

	`cd /var/www/html/cataloging
	sudo nano .htaccess`

	4. Adding the neccessary information and checking it enables the password to be
	required when going to the cataloging module.

5. All of this enables the user to be able to add cataloging entries after entering the
required password

#### Key Details

* making sure security is correct with the small change in the security of apache2 from
**none** to **all**

* including the correct data in the cataloging module (author, title, publisher, copyright)

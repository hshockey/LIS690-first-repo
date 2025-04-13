# Installing Wordpress

## Steps for install

1. make sure **php** and **mysql** are the updated version, along with **Ubuntu** with

	* `cat /etc/issue.net`

2. restart **apache2** and **mysql**

3. download the zip of wordpress, which includes extracting the program with

	* `sudo unzip latest.zip`

4. switch to **mysql** server where you create a user, password, and database

	* For this part, I didn't catch the specific words to use for the user and database,
	 so at first I entered it wrong. This resulted in a server that obviously didn't
	 work. Eventually, I went back to the instruction video and got the right answer. 

* I decided not to rename my wordpress directory, since I was already having issues before
 this.

5. change file ownership: `sudo chown -R www-data:www-data /var/www/html/wordpress`

6. check URL with new addition:

	* `http://http://35.223.220.222/wordpress/index.php/world-of-words-library/`

	* This was also where I had an error multiple times. I think it stemmed from not
	 having the right information for the user and database, but it took me a couple
	 tries to get the URL to work.

* Overall, the process wasn't too difficult, it's always the smallest things that trip
me up, but I was ultimately able to get my wordpress up and running. 

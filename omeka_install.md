# Omeka Install Notes

* Made sure the system was updated with `sudo apt update` and that **PHP** and **MySQL**
had the correct versions installed.

* Install imagemagick (this works with photo files):

	`sudo apt install imagemagick`

	* Note that this took me four times because every time I kept messing up a small
	part of the code even though it was such a small command. Always focus on detail.

* `sudo a2enmod rewrite` will allow apache to rewrite URLs to make them user friendly.

	* Have to restart apache2 to implement this.

## Instructions

1. To start, I went back to where we installed the original **opacdb** and **opacuser**
redid the steps but with the new **omekadb** and **omekauser**.

2. Then, once I gave privileges like before, I created a table titled "popular manga" which
includes the same rows but with different information.

	1. I always have to remember that when I go into mysql, I have to go to my database
	through `use omekadb;` before it'll actually go into it.

3. Next, adding the information became easier for me since I had already done it once with
this formula command:

	`insert into popular manga (author, title, copyright) values / ('author','title',
	'copyright year')`

4. I downloaded the zip file for omeka, where I followed the same steps used for wordpress
and extracted the zip with `upzip`.

5. Replace the values of all database credentials in the `db.ini` file.

	* This is where I got the most confused, but when I stopped to think about how this
	worked for wordpress and created the ILS, I realized that I needed to use `sudo
	nano db.ini`. This was probably the moment I felt most competent and proud of what 
	I figured out on my own!

6. Finally, I used `chown` command and made sure the user and owner were both `www-data`

### Findings

The rest of the process was straightforward, especially once I got to my URL and it worked:
`http://35.223.220.222/omeka-3.1.2`

The rest involved personalizing the site and linking it to wordpress.

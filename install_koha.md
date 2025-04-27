# Install Koha Notes

1. Set up a new virtual machine

	1. stay on ubuntu 22.04.5 LTS and add **Series E2**, **Machine Type 2 vCPU 4 GB memory**, and **20GB disk size**

	2. add the tag `koha-8080` to **Network tags**

2. Set up firewall
	* This will allow traffic to port 8080

	1. Through the VPN Network, you have to add a **firewall policy** with the name `koha-opac`

	2. The description should be **open port 8080 for the OPAC**

	3. For the target tags, include `koha-8080`

	4. And in the source ranges, add **0.0.0.0/0**

	5. Add **8080** in the ports box

3. Installing Koha Repo

	1. make sure everything is updated

	2. to save disk space, use the two following commands:

		`sudo apt autoremove -y && sudo apt clean`

		`sudo apt install gnupg2 apt-transport-https`

	3. reboot server

4. Koha Repository
	* This is where I really started to struggle. I realized a bit later that I had created the wrong server type, instead of Utuntu 22.04.5. I had to create a new server to make sure I was getting the right information.

	1. go to root with `sudo su`

	2. add the repository: `echo 'deb http://debian.koha-community.org/koha stable main' | sudo tee /etc/apt/sources.list.d/koha.list`

	3. install GPG key: `wget -qO- https://debian.koha-community.org/koha/gpg.asc | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/koha.gpg > /dev/null`

5. Now Install Koha

	1. install koha-common with `apt install koha-common`

6. Configure Koha

	1. create a backup first: `cd /etc/koha/` ` cp koha-sites.conf koha-sites.conf.backup` 

	2. bring up nano to configure the document: `nano /etc/koha/koha-sites.conf`

	3. Change `INTRAPORT="80"` to `INTRAPORT="8080"`

	4. install mysql server, where you add a password for the site: `boobooK20!`

	5. Bring in **Apache**

		1. enable URL rewriting and CGI: `a2enmod rewrite` and `a2enmod cgi`

		2. restart apache2

	6. Create a database for Koha: `koha-create --create-db bibliolib`

	7. In notes for apache2, you need to add `Listen 8080` under `Listen 80` and check to make sure the configurations worked with `apachectl configtest`


7. Koha Web Installer

	1. Get username and password in nano to access online database: `nano /etc/koha/sites/bibliolib/koha-conf.xml`

	2. Use `http://35.223.76.190:8080` to access web installer

	3. Follow install instructions to create online Koha database.

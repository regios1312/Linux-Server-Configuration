
1.URL: http://52.66.199.113.xip.io

------------------------------------------------
SOFTWARE INSTALLED

1.Installed apache2 on the server using [sudo apt-get install apache2] command.
2.Installed mod_wsgi application handler and python development tools using [sudo apt-get install libapache2-mod-wsgi python-dev] command.
3.Installed git.
4.Installed flask and sqlalchemy using [sudo apt-get install python-pip python-flask python-sqlalchemy] command.
5.Installed httplib2 by sudo pip install oauth2client requests httplib2 command.
6.Installed sqlite using [sudo apt-get install sqlite3 libsqlite3-dev] command.(Have used sqlite instead of postgresql)

-------------------------------------------------

Configurations made:
1.Configured the timezone to UTC using [sudo dpkg-reconfigure tzdata] command.
2.To configure ssh to a non-default port 1st went to the networking Tab of Lightsail and added a custom port set to 2200.
(This was done so as to not get locked out of the system)
3.Then went and set the ssh port to 2200 by using command [sudo nano /etc/ssh/sshd_config] and changed the default port setting.
4.To change the firewall setting added the following command in sequence:
   sudo ufw default deny incoming
   sudo ufw default allow outgoing
   sudo ufw allow 2200/tcp
   sudo ufw allow 80/tcp
   sudo ufw allow 123/udp
5.Then enabled the firewall using [sudo ufw enable] command.
6.Added a user grader using [sudo adduser grader] command.
7.Added the following to the visudo file in privilege specification:
	grader  ALL=(ALL:ALL) ALL
8.Created a wsgi file in [/var/www/CatalogApp/CatalogApp/] directory by name catalogapp.wsgi(see the contents of the file for overview).
9.Setup a virtual host file [path:/etc/apache2/sites-available/itemsCatalog.conf].
10.Cloned my repository for item catalog project into /var/www/CatalogApp.
11.Updated the Client_id and oauth_flow in flaskapp.py program.
12.Created a key pair for grader using ssh-keygen command.

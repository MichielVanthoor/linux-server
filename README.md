# linux-server

This project only contains a README-file with the steps needed to access a web application hosted on Google Cloud.

* You can connect to the server using following IP Address and SSH port:
  * IP Address: `35.204.112.13`
  * SSH port: `2200`
* The complete URL to my hosted web application is http://35.204.112.13/
* The software installed and configuration changes made, consist of:
  * Adding the grader user `sudo adduser grader`
  * Giving admin rights to grader user
     * Create new config file `sudo touch /etc/sudoers.d/grader`
     * Insert `grader ALL=(ALL) NOPASSWD:ALL` in this file using your favorite text editor
  * Configuring firewall rules to allow SSH (port 2200), HTTP (port 80), and NTP (port 123) connections
  * Configuring `/etc/ssh/sshd_config` using your favourite text editor
      * Change the default SSH Port in to port `2200`
      * Change `#PermitRootLogin no` to `PermitRootLogin yes`
      * Reboot the server to reconfigure the settings `sudo reboot`
  * Generating Public and Private key on client with `ssh-keygen` command
      * Place the public key on the server using [these steps](https://cloud.google.com/compute/docs/instances/adding-removing-ssh-keys)
  * Install Apache HTTP web server `sudo apt-get install apache2`
  * Install Web Server Gateway interface `sudo apt-get install libapache2-mod-wsgi`
  * Install the application
      * Change directory `cd /var/www`
      * Clone application from Github `sudo git clone https://github.com/MichielVanthoor/catalog_app`
      * Add `WSGIScriptAlias / /var/www/catalog_app/vagrant/catalog/catalog_app.wsgi` to the `/etc/apache2/sites-enabled/000-default.conf` file
      * Restart Apache with `sudo apache2ctl restart`
  * Install the requirements for running the application
      * `sudo apt-get install python-pip`
      * `sudo dpkg-reconfigure locales`
      * `sudo pip install SQLAlchemy`
      * `sudo pip install Flask`
      * `sudo pip install oauth2client`
      * `sudo apt-get install sqlite3 libsqlite3-dev`
* The private key needed to connect to the server can be obtained by reaching out to michielvanthoor@gmail.com

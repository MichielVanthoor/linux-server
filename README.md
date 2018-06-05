# linux-server

This project only contains a README-file with the steps needed to access a web application hosted on Google Cloud.
The web application itself can be found [here](https://github.com/MichielVanthoor/catalog_app).

* You can connect to the server using following IP Address and SSH port:
  * IP Address: ``
  * SSH port: ``
* The complete URL to my hosted web application is http://
* The software installed and configuration changes made, consist of:
  * Add the grader user `sudo adduser grader`
  * Give admin rights to grader user
     * Create new config file `sudo touch /etc/sudoers.d/grader`
     * Insert 'grader ALL=(ALL) NOPASSWD:ALL' in this file using your favorite text editor
     * Public and Private key generated using ``
  * Configured firewall rules to allow SSH (port 2200), HTTP (port 80), and NTP (port 123) connections
  * `TODO`Change the default SSH Port in `/etc/ssh/sshd_config` to port `2200`
     * 


     
* List of third-party resources used
  *
  * 
 
* The private key needed to connect to the server can be obtained by reaching out to michielvanthoor@gmail.com

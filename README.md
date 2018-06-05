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
      * `TODO`Change the default SSH Port in to port `2200`
      * Change `#PermitRootLogin no` to `PermitRootLogin yes`
      * `TODO`Reload this config using `/etc/init.d/sshd restart`
  * `TODO` Generating Public and Private key on client machine


     
* List of third-party resources used
  * [The Deployed Web Application The web application](https://github.com/MichielVanthoor/catalog_app).
 
* The private key needed to connect to the server can be obtained by reaching out to michielvanthoor@gmail.com

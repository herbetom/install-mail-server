# Install Software on Debian Server


Script for the automated install and first configuration of software on an Debian Server.

It will install the following:
- htop
- zip, unzip
- git
- locate

And the following things optional:
- docker
- Webmin
- Apache2, PHP 7.0, certbot (Apache)
- mailcow: dockerized (https://github.com/mailcow/mailcow-dockerized)

## Before you start:
If you plan on Installing Mailcow you should before you start the installation update your DNS according to the following 
minimal DNS configuration. Also you maybe have to wait that the DNS Servers used by LetsEncrypt are updated before you start. 
Otherwise you will probably have problems while the installation because the LetsEncypt client will run into errors.  

https://mailcow.github.io/mailcow-dockerized-docs/prerequisite-dns/#the-minimal-dns-configuration


## How To Use:

Type the following in the console

`bash <(wget -qO- https://raw.githubusercontent.com/herbetom/install-debian-server/master/install.sh)`

During the installation the script will ask you what you want to install (yes or now). 

If you install Mailcow you will get asked what Hostname (FQDN) you want to use. I personaly use usually something like `mail.example.org'.

## Additional Infos
### Mailcow
- Mailcow gets installed into `/opt/mailcow-dockerized/`
- If you want to update Mailcow you should do according to [Mailcow: Automatic update](https://mailcow.github.io/mailcow-dockerized-docs/install-update/#automatic-update) the following:
  - go into the Mailcow directory `cd /opt/mailcow-dockerized/`
  - `./update.sh`
  - if updates where found (you have to read the output) you have to run `./update.sh` 
  - you will have to allow stopping all Mailcow Docker Containes with `y`.
  - now it will update and start Mailcow again after it has finished.

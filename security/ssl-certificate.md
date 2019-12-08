# Install let's encript certificate in ubuntu 18.04

## Prerequisites
* Apache installed
* Open ports 80 and 433

## SSH into the server
SSH into the server running your HTTP website as a user with sudo privileges.
    
    ssh -i pemfile.pem user@host

## Add Certbot PPA
You'll need to add the Certbot PPA to your list of repositories. To do so, run the following commands on the command line on the machine:

    sudo apt-get update
    sudo apt-get install software-properties-common
    sudo add-apt-repository universe
    sudo add-apt-repository ppa:certbot/certbot
    sudo apt-get update

## Install Certbot
Run this command on the command line on the machine to install Certbot.

    sudo apt-get install certbot python-certbot-apache

## Install and configure certificate
Run this command to get a certificate and have Certbot edit your Apache configuration automatically to serve it, turning on HTTPS access in a single step.

    sudo certbot --apache

### Just get a certificate
    sudo certbot certonly --apache

### Agregar certificado en archivo de configuraion de apache
    /etc/apache2/sites-available/default-ssl.conf

### Enable ssl-mudule an restart apache

    sudo a2enmod ssl
    sudo a2ensite default-ssl
    sudo service apache2 restart


## Test automatic renewal
sudo certbot renew --dry-run

The command to renew certbot is installed in one of the following locations:

/etc/crontab/
/etc/cron.*/*
systemctl list-timers

## Additional Info:

https://letsencrypt.org/how-it-works/

https://certbot.eff.org/lets-encrypt/ubuntubionic-apache
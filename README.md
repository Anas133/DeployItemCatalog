Project Description:

This projecj will deploy the item catalog project in DigitalOcean cloud,
with Ubuntu 16.04.5 x64 OS.

Summary of software installed:

sudo apt-get update

sudo apt-get upgrade

sudo apt-get autoremove

sudo apt-get install finger

sudo adduser grader

- grant grader user access as sudo

sudo cp /etc/sudoers.d/90-cloud-init-users /etc/sudoers.d/grader

sudo nano /etc/sudoers.d/grader
editing 90-cloud-init-users to grader

- generate a key pair locally

ssh-keygen

- install the public key

mkdir .ssh

touch .ssh/authorized_key

* back to local machine and read the conent of the public key 
in the ssh-keygen by --> cat .ssh/id_rsa.pub *

copy it and past it in .ssh/authorized_key

chmod 700 .ssh
chmod 644 .ssh/authorized_key

* disable a passwords in the user account:

sudo nano /etc/ssh/sshd_config

in the line password authentication yes --> to no

sudo service ssh restart

* for firewall:

sudo ufw status

sudo ufw default deny incoming

sudo ufw default allow outgoing

sudo ufw allow ssh

sudo ufw allow 2200/tcp

sudo ufw allow www

sudo ufw allow ntp

sudo ufw enable

And for a summary of Configuration made and other software installed is in the following URL:

https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps

- The ip adderss is 167.99.98.64
- And you can access the website through this URL : http://167.99.98.64.xip.io

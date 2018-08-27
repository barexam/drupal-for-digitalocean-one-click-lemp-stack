# drupal-for-digitalocean-one-click-lemp-stack
A script to seamlessly deploy Drupal 8 (or 7) on a DigitalOcean LEMP stack.
------------------------------------------------------------------------------------------------------------------------------

**To get started:**

Head over to DigitalOcean (https://www.digitalocean.com) & spin up a “one-click” LEMP stack droplet. Once it's deployed, use your preferred CLI to SSH into your server, i.e.:
```
ssh root@YOUR_DIGITALOCEAN_IP_ADDRESS -i ~/.ssh/id_rsa
```
Once connected, use the CLI to run either of the following commands:

**For Drupal 8:**
```
sudo wget https://raw.githubusercontent.com/jdhakert/drupal-for-digitalocean-one-click-lemp-stack/master/install-drupal-8.sh && sudo chmod +x install-drupal-8.sh && sudo yes "yes" | sudo ./install-drupal-8.sh
```
**For Drupal 7:**
```
sudo wget https://raw.githubusercontent.com/jdhakert/drupal-for-digitalocean-one-click-lemp-stack/master/install-drupal-7.sh && sudo chmod +x install-drupal-7.sh && sudo yes "yes" | sudo ./install-drupal-7.sh
```
Once it has successfully completed, point your browser to ```http://YOUR_DIGITALOCEAN_IP_ADDRESS/phpmyadmin``` and finish the Drupal installation.

You may retrieve your login password string by running the following command (your login username will be ```root``` by default):
```
cat ~/.digitalocean_password
```
**Important Final Step:**
After Drupal has installed, be sure to execute the following command to secure your ```settings.php``` file:
```
chmod 644 /var/www/html/drupal/sites/default/settings.php
```

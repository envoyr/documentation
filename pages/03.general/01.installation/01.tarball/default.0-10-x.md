---
title: 'Install froxlor from Tarball'
---

## 0. Prerequisites

For a manual installation, you need to have a recent webserver (apache2 or nginx) with PHP and MySQL/MariaDB-server running.

You should also have at least one (sub-)domain available to use as froxlor's main system hostname (FQDN). This (sub-)domain _cannot_ be used for customers or hosting websites/e-mails. In case you want to use e.g. **mydomain.tld** yourself for your website and email accounts etc. you can just use a subdomain like **froxlor.mydomain.tld** in the installation process. This way, **mydomain.tld** can be added as a domain for a customer.

## 1. Download the tarball

You can download the latest version of froxlor from [https://files.froxlor.org/releases/](https://files.froxlor.org/releases/)

````shell
# change directory
cd /var/www/

# download latest froxlor version
wget https://files.froxlor.org/releases/froxlor-latest.tar.gz

# the content should go in to the folder /var/www/froxlor
# note: the archive contains the folder 'froxlor' already!
tar xvfz froxlor-latest.tar.gz

# remove archive
rm froxlor-latest.tar.gz
````

## 2. Set Permissions

In order for the webserver to be able to server the files, the owner must be set correctly. Note: If you're using FCGID/PHP-Fpm for the froxlor-Vhost, you have to replace the webserver-user with your local froxlor-user.

````shell
chown -R [webserver-user]:[webserver-user] /var/www/froxlor/
````

(the 'webserver-user' on most systems is 'www-data' or 'apache')

## 3. Installation via Web-Installer

<div class="bg-yellow-200 text-grey-dk-300 p-3 mt-3"><b>Note:</b> On some distributions, the default web-root directory differs from <b>/var/www/</b>. To access froxlor, you need to adjust the default virtual-host to set <b>/var/www/</b> as document-root.</div>

Now that you have extracted all the files you are ready to (re)start the webserver. You should now be able to access froxlor via `http://{your-ip-address}/froxlor` Just follow the installation-process and froxlor will be installed in no time.

The _unprivileged_ MySQL user does not need to exist, it will be created using the provided root-privileged user by the installation process.

## 4. Settings before configuration!

**It is very important that you first adjust all settings** according to your needs before configuring the services. This is because some configuration-templates/commands change dynamically depending on the settings you chose.

To adjust settings, login as admin and click on 'Settings' in the menu on the left side.

If you now chose to use PHP via FCGID or FPM, then you should also read our fcgid/php-fpm handbooks:

* [Apache2 / FCGID](/general/configuration/fcgid.html)
* [Apache2 & nginx / PHP-FPM](/general/configuration/php-fpm.html)

## 5. Configuration of services

&#8594; see [Configuration Guide](/general/configuration/index.html)

## 6. Need help?
If you run into any problems or have difficulties understanding / setting-up / whatever - don't hesitate to contact us either via e-mail ([team@froxlor.org](mailto:team@froxlor.org)) or the preferred way: on Discord ([https://discord.froxlor.org](https://discord.froxlor.org)) and our forums ([https://forum.froxlor.org/](https://forum.froxlor.org/))
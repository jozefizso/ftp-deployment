FTP deployment
==============

FTP deployment is a tool for automated deployment of web applications to an FTP server.
It requires PHP 5.3 or newer.

This fork of the [dg/ftp-deployment](https://github.com/dg/ftp-deployment) tool is enhanced with include files patterns.
In my use case I needed to explicitly specify just directories and files I wanted to synchronize to the FTP server so I added a new `include` settings to the `deployment.ini` file, instead of listing all the directories I needed to exclude from synchronization.


Usage
-----

Create file `deployment.ini` according to the instructions in `deployment.sample.ini` and run:

	php deployment.php deployment.ini


### Nette application

Sample configuration for including files in Nette application, where `app` and `libs` directories are in the root of the web application.
This configuration does not sync `.htaccess` file in the root of the web application.

    include = "
        /app
        /css
        /js
        /libs
        /log/.htaccess
        /temp/.htaccess
	/index.php
	/favicon.ico
    "
    
    ignore = "
        .git*
        .DS_Store
	config.local.neon
    "
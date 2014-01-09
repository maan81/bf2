To install bf2 [ where bf2 is the name of the current project ] :

 - Place the folder in `` /var/www/ ``

 - in `` /etc/hosts ``, add  `` 127.0.0.1	bf2 ``

 - copy `` /etc/apache2/sites-available/default.conf `` to `` /etc/apache2/sites-avilaible/bf2.conf ``

 - uncomment and update the `` ServerName localhost `` to `` Server bf2 ``

 - update `` DocumentRoot /var/www/bf2/public `` to `` DocumentRoot /var/www/ ``

 - update file `` /etc/hosts `` to add line `` 127.0.0.1	bf2 ``

 - run command `` sudo a2ensite bf2 ``; `` sudo a2dissite default ``; `` sudo a2ensite default ``; `` sudo service apache restart ``



The few changes I have made after the basic installation : 

 - Database settings in ./application/config/database.php:
   - $db['default']['hostname'] = 'localhost';
   - $db['default']['username'] = 'root';
   - $db['default']['password'] = 'password';
   - $db['default']['database'] = 'bf2';

 - Added server port in ./index.php
   - $install_url = 'http'.((empty($_SERVER['HTTPS']) or $_SERVER['HTTPS'] == 'off')?'':'s') .'://'. $_SERVER['SERVER_NAME'] .':'. $_SERVER['SERVER_PORT'] .'/public/';

 - Modified the base url and index page in ./application/config/config.php
   - $config['base_url']	= 'http://localhost:8000';
   - $config['index_page'] = "";

 - Installed the DB
 
 - Renamed ./public/1.htaccess to ./public/.htaccess
 
 - Copied [the file which I just renamed] ./public/.htaccess to ./.htaccess

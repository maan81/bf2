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

#Set docker .Env

cd ~/Project/Fullstack2023/Wordpress

### Set Rules

```
# BEGIN WordPress
# The directives (lines) between "BEGIN WordPress" and "END WordPress" are
# dynamically generated, and should only be modified via WordPress filters.
# Any changes to the directives between these markers will be overwritten.
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
php_value upload_max_filesize 328M
php_value post_max_size 328M
php_value memory_limit 256M
php_value max_execution_time 300
php_value max_input_time 300
</IfModule>

# END WordPress
```

### Setup upload bandwidth
@ini_set( 'upload_max_filesize' , '300M' );
@ini_set( 'post_max_size', '300M');
@ini_set( 'memory_limit', '300M' );
@ini_set( 'max_execution_time', '300' );
@ini_set( 'max_input_time', '300' );

define('FS_METHOD', 'direct');


### Change mode
sudo chown -R ducmy:ducmy ~/Project/Fullstack2023/Wordpress

### Use git.
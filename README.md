# mytrius-integration
Wordpress Plugin allowing the Mytrius ERP integration with WooCommerce
Developed and maintained by Thiago Mello - Vizad

Using the API documented here: http://wsdoc.mitryusweb.com.br/Doc

Add and refresh all data.

1) SSH to the server 
2) Test running the wp-cron.php script and see if it returns an error
<pre>php /var/www/html/wp-cron.php</pre>
3) Run command Crontab for the Apache user (www-data)
<pre> sudo crontab -u www-data -e</pre>
3) Create the following line which will add a CRON job to refresh every 3 minutes:
<pre>
*/3 * * * * php /var/www/html/wp-cron.php
</pre>
4) Save and disable the Wordpress CRON adding the following line in your wp-config.php:
<pre>
define(‘DISABLE_WP_CRON’, true);
</pre>


Remember that Crontab executes the task using the current user that ran crontab -e. When you use wget it's handled by Apache using the www-data user/group pair.


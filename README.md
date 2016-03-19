# mytrius-integration
Wordpress Plugin allowing the Mytrius ERP integration with WooCommerce
Developed and maintained by Thiago Mello - Vizad

Using the API documented here: http://wsdoc.mitryusweb.com.br/Doc

Add and refresh all data.

1) SSH to the server 
2) Run command 
<pre> sudo crontab  -e</pre>
3) Create the following line which will add a CRON job to refresh every 3 minutes:
<pre>
*/3 * * * * root /var/www/html/wp-cron.php
</pre>
4) Save and disable the Wordpress CRON adding the following line in your wp-config.php:
<pre>
define(‘DISABLE_WP_CRON’, true);
</pre>

# Forcing 'https://'

Redirect from the 'http://' to 'https://' version of the URL.

## Code

	# Redirect from the `http://` to the `https://` version of the URL.
	<IfModule mod_rewrite.c>
		RewriteEngine On
		RewriteCond %{HTTPS} !=on
		RewriteRule ^(.*)$ https://%{HTTP_HOST}/$1 [R=301,L]
	</IfModule>

## Issues with your localhost or tdlinx.wtf?

If you add the https redirect to your project, you're going to have some issues on your localhost and tdlinx.wtf because they don't have https... well, add the following line __RewriteCond__ (replace __tdbenew6t692__ with your project's jobcode):

	# Redirect from the `http://` to the `https://` version of the URL.
	<IfModule mod_rewrite.c>
		RewriteEngine On
		RewriteCond %{HTTP_HOST} !tdbenew6t692
		RewriteCond %{HTTP_HOST} !localhost
		RewriteCond %{HTTPS} !=on
		RewriteRule ^(.*)$ https://%{HTTP_HOST}/$1 [R=301,L]
	</IfModule>

When you don't want to update the jobcode in each project, this might be better:

	# Redirect from the `http://` to the `https://` version of the URL.
	<IfModule mod_rewrite.c>
		RewriteEngine On
		RewriteCond %{HTTP_HOST} !\.(int|wtf)$
		RewriteCond %{HTTP_HOST} !localhost
		RewriteCond %{HTTPS} !=on
		RewriteRule ^(.*)$ https://%{HTTP_HOST}/$1 [R=301,L]
	</IfModule>

## Source

[https://wiki.apache.org/httpd/RewriteHTTPToHTTPS](https://wiki.apache.org/httpd/RewriteHTTPToHTTPS)
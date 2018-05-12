# Forcing 'https://'

Redirect from the 'http://' to 'https://' version of the URL.

## Code

	# Redirect from the `http://` to the `https://` version of the URL.
	<IfModule mod_rewrite.c>
		RewriteEngine On
		RewriteCond %{HTTPS} !=on
		RewriteRule ^(.*)$ https://%{HTTP_HOST}/$1 [R=301,L]
	</IfModule>

## Issues with your localhost?

	# Redirect from the `http://` to the `https://` version of the URL.
	<IfModule mod_rewrite.c>
		RewriteEngine On
		RewriteCond %{HTTP_HOST} !localhost
		RewriteCond %{HTTPS} !=on
		RewriteRule ^(.*)$ https://%{HTTP_HOST}/$1 [R=301,L]
	</IfModule>

Another option:

	# Redirect from the `http://` to the `https://` version of the URL.
	<IfModule mod_rewrite.c>
		RewriteEngine On
		RewriteCond %{HTTP_HOST} !\.(local)$
		RewriteCond %{HTTP_HOST} !localhost
		RewriteCond %{HTTPS} !=on
		RewriteRule ^(.*)$ https://%{HTTP_HOST}/$1 [R=301,L]
	</IfModule>

## Source

[https://wiki.apache.org/httpd/RewriteHTTPToHTTPS](https://wiki.apache.org/httpd/RewriteHTTPToHTTPS)

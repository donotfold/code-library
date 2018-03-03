# Rewrite root files to a specific folder

Browsers, scripts, sites, etc can require that you add files to the root folder of your site (for example: favicon.ico in your root folder).
The following .htaccess script can redirect the files to a specific folder so your root folder will stay clean. __Do it, sherlock!__

## Code

	# URL rewrite
	<IfModule mod_rewrite.c>
		RewriteEngine on
		RewriteCond %{REQUEST_FILENAME} !-f
		RewriteCond %{REQUEST_FILENAME} !-d
		RewriteCond %{DOCUMENT_ROOT}/resources/icons/%{REQUEST_URI} -f
		RewriteRule ^(.*)$ resources/icons/$1 [NC,L]
	</IfModule>

## Developer

+ [Stijn Van Minnebruggen](http://donotfold.be)

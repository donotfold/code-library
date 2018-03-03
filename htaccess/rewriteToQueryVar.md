# Rewrite everything to the index with a queryVar

Rewrite everything (that doesn't actually exist) in your URL to /index.php with a queryVar.

## Code

	# URL rewrite
	<IfModule mod_rewrite.c>
		RewriteEngine on
		RewriteCond %{REQUEST_FILENAME} !-f
		RewriteCond %{REQUEST_FILENAME} !-d
		RewriteRule ^(.*)\/{0,1}$ /index.php?queryVar=$1 [QSA,NC,L]
	</IfModule>

## Developer

+ [Stijn Van Minnebruggen](http://donotfold.be)

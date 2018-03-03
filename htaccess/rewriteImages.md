# Rewrite images that don't exist to a fallback image

Instead of image errors you can use the following rewrite code to rewrite your dead links to a fallback image.

## Code

	# Image fallback
	<IfModule mod_rewrite.c>
		RewriteEngine on
		RewriteCond %{REQUEST_FILENAME} !-f
		RewriteRule ^(.*)\.(gif|png|jpg)$ fallback.png [NC,L]
	</IfModule>

## Developer

+ [Stijn Van Minnebruggen](http://donotfold.be)

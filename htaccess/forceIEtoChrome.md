# Remove the X-UA-Compatible meta tag from your html

The X-UA-Compatible meta tag from your html can be removed by using an htaccess rule instead.
The tag makes sure your Internet Explorer browser uses the specified browser rendering instead of the one used in the active browser.

## How To?!

Instead of adding the following meta tag to your html (which will not validate in W3C):

	<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />

You can easily add these lines of code to your .htaccess file:

	# set X-UA-Compatible for IE
	<IfModule mod_headers.c>
		Header set X-UA-Compatible "IE=Edge,chrome=1"
		<FilesMatch "\.(appcache|crx|css|eot|gif|htc|ico|jpe?g|js|m4a|m4v|manifest|mp4|oex|oga|ogg|ogv|otf|pdf|png|safariextz|svg|svgz|ttf|vcf|webm|webp|woff|xml|xpi)$">
			Header unset X-UA-Compatible
		</FilesMatch>
	</IfModule>

## Developer

+ [Stijn Van Minnebruggen](http://donotfold.be)

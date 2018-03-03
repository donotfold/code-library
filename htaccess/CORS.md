# Allow cross-origin requests

Add the following code to your .htaccess file if you want to allow cross-origin requests.

## Code

	# Allow cross-origin requests for get.
	<IfModule mod_headers.c>
		Header set Access-Control-Allow-Origin "*"
	</IfModule>
	
    # Allow cross-origin requests for post.
    <IfModule mod_headers.c>
        Header set Access-Control-Allow-Origin "*"
        Header set Access-Control-Allow-Headers "Origin, X-Requested-With, Content-Type, Accept"
    </IfModule>

## Optional

If you only want to allow a specific content type you can do the following code:

	# Allow cross-origin access to web fonts.
	<IfModule mod_headers.c>
		<FilesMatch "\.(eot|otf|tt[cf]|woff2?)$">
			Header set Access-Control-Allow-Origin "*"
		</FilesMatch>
	</IfModule>

## Source

+ https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS
+ http://enable-cors.org/
+ http://www.w3.org/TR/cors/

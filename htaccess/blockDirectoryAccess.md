# Block access to directories without a default document

Add the following code to your .htaccess file if you want to disable anyone from surfing through every directory on your server (which may include rather private places such as the CMS's directories).

## Code

	# Block anyone from viewing folder content with no default document
	<IfModule mod_autoindex.c>
		Options -Indexes
	</IfModule>


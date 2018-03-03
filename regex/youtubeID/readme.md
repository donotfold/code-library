# YouTube ID

Get YouTube ID from URL.
These are the types of URLs supported:

	http://www.youtube.com/watch?v=0zM3nApSvMg&feature=feedrec_grec_index
	http://www.youtube.com/user/IngridMichaelsonVEVO#p/a/u/1/QdK8U-VIH_o
	http://www.youtube.com/v/0zM3nApSvMg?fs=1&amp;hl=en_US&amp;rel=0
	http://www.youtube.com/watch?v=0zM3nApSvMg#t=0m10s
	http://www.youtube.com/embed/0zM3nApSvMg?rel=0
	http://www.youtube.com/watch?v=0zM3nApSvMg
	http://youtu.be/0zM3nApSvMg

## Regular expression

	/^.*((youtu.be\/)|(v\/)|(\/u\/\w\/)|(embed\/)|(watch\?))\??v?=?([^#\&\?]*).*/

## Javascript function

	function youtubeID(url) {
		var regExp = /^.*((youtu.be\/)|(v\/)|(\/u\/\w\/)|(embed\/)|(watch\?))\??v?=?([^#\&\?]*).*/,
			match = url.match(regExp);
		return (match && match[7].length == 11)? match[7] : false;
	}

## Source

http://stackoverflow.com/questions/3452546/javascript-regex-how-to-get-youtube-video-id-from-url

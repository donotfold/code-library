# Angular URL fixer pipe

This Angular pipe fixes broken or dumbass URL's to correct URL's.

## What?!

The pipe validates and fixes URL's like:
- no http:// (Change 'www.donotfold.be' or 'donotfold.be' to 'http://www.donotfold.be' or 'http://donotfold.be')
- broken links (http//www.thesedays.com or https//www.sjarel.com)
- Changes: '//link.com' to 'http://link.com'

## Code

	import { Pipe } from '@angular/core';

	@Pipe({ name: 'url' })

	export class urlValidator {

		transform(str:any) {

			// validate and fix URL's like:
			// - no http:// (www.donotfold.be or donotfold.be)
			// - broken links (http//www.thesedays.com or https//www.sjarel.com)
			// - //link.com

			let findArr:string[] = ['http//', 'https//'];
			let replArr:string[] = ['http://', 'https://'];

			findArr.map(function(val, i) { str = str.replace(val, replArr[i]); });
			if(str.indexOf('//') === 0) { str = 'http:' + str; }
			if(str.indexOf('http') === -1) { str = 'http://' + str; }

			return str;

		}

	}

## Developers

+ [Stijn Van Minnebruggen](http://donotfold.be)
+ [Bram Verdyck](https://twitter.com/troti13)

## License

This script is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).

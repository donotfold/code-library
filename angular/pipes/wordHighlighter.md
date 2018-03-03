# Angular word highlighter pipe

This Angular pipe highlights words like MAGIC ;)

## Code

	import { Pipe } from '@angular/core';

	@Pipe({ name: 'highlight' })

	export class highlightPipe {

		transform(str:any, args?:any) {

			var pattern = args.replace(/[\-\[\]\/\{\}\(\)\*\+\?\.\\\^\$\|]/g, "\\$&");
			pattern = pattern.split(' ').filter((t) => { return t.length > 0; }).join('|');
			var regex = new RegExp(pattern, 'gi');
			return args ? str.replace(regex, (match) => `<strong>${match}</strong>`) : str;

		}

	}

## Developers

+ [Bram Verdyck](https://twitter.com/troti13)
+ [Stijn Van Minnebruggen](http://donotfold.be)

## License

This script is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).

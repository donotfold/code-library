# Angular comma separated list pipe

This Angular pipe returns a comma separated link of your array

## Code

	import { Pipe } from '@angular/core';

	@Pipe({ name: 'commaseparatedlist' })

	export class csListPipe {

		transform(list:any) {

			let listObj:any = Object.create(list || []);

			listObj = listObj.toString();
			listObj = listObj.replace(/,/g, ', ');

			return listObj;

		}

	}

## Developers

+ [Stijn Van Minnebruggen](http://www.donotfold.be)

## License

This script is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).

# Angular Big Numbers pipe

This Angular pipe changes big numbers (thousands, millions, etc) to K and M values.

## What?!

The pipe changes numbers like 123456 to 124k.

## Code

	import { Pipe } from '@angular/core';

	@Pipe({ name: 'bigNumber' })

	export class bigNumberPipe {

		transform(num:number, digits:number=1) {

			let si:any = [
				{ value: 1E18, symbol: "E" },
				{ value: 1E15, symbol: "P" },
				{ value: 1E12, symbol: "T" },
				{ value: 1E9,  symbol: "G" },
				{ value: 1E6,  symbol: "M" },
				{ value: 1E3,  symbol: "k" }
			];

			let rx = /\.0+$|(\.[0-9]*[1-9])0+$/;
			let ret:string|boolean = false;

			si.forEach(siv => {

				if(num >= siv['value']) {

					ret = (num / siv['value']).toFixed(digits).replace(rx, "$1") + siv['symbol'];
					return;

				}

			});

			return ret || num.toFixed(digits).replace(rx, "$1");

		}

	}


## Developers

+ [Stijn Van Minnebruggen](http://donotfold.be) [via](http://stackoverflow.com/questions/9461621/how-to-format-a-number-as-2-5k-if-a-thousand-or-more-otherwise-900-in-javascrip)

## License

This script is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).

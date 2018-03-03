# Angular URL domain pipe

This Angular pipe returns domain.tld from full URL's

## Code

	import { Pipe, PipeTransform } from '@angular/core';

	@Pipe({
		name: 'domain'
	})
	export class DomainPipe implements PipeTransform {

		transform(value: any, args?: any): any {
			let domain;
			//find & remove protocol (http, ftp, etc.) and get domain
			if (value.indexOf("://") > -1) {
				domain = value.split('/')[2];
			} else {
				value = value.split('/')[0];
			}

			//find & remove port number
			domain = domain.split(':')[0];

			return domain;
		}

	}

## Developers

+ [Bram Verdyck](https://twitter.com/troti13)

## License

This script is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).

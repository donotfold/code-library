# Angular SafePipe

This Angular pipe allows you to do unsafe inserts ;)

## What?!

You can use the pipe for for example youtube video embeds like this:

	<iframe width="560" height="315" [src]="videoURL | safe" frameborder="0" allowfullscreen></iframe>

## Code

	import { Pipe, PipeTransform } from '@angular/core';
	import { DomSanitizer} from '@angular/platform-browser';

	@Pipe({ name: 'safe' })

	export class SafePipe implements PipeTransform {
		constructor(private sanitizer: DomSanitizer) {}
		transform(url) {
			return this.sanitizer.bypassSecurityTrustResourceUrl(url);
		}
	}

Make sure your pipe is set in the AppModule:

	@NgModule({
		declarations : [
			...
			SafePipe
		],
	})

## Developers

+ [Stijn Van Minnebruggen](http://donotfold.be) ([via](https://stackoverflow.com/questions/38037760/how-to-set-iframe-src-in-angular-2-without-causing-unsafe-value-exception))

## License

This script is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).

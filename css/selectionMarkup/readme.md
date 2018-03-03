# Selection markup CSS

Use this css code if you want to apply selection markup code to your stylesheet.

## CSS Code

	::-moz-selection { background-color: red; color: blue; text-shadow: none; }
	::selection { background-color: red; color: blue; text-shadow: none; }

## Sass mixin

	@mixin selection($background, $color, $element:false) {
		// if $element = true, mixin can be used inside an element, else place in root
		@if $element == true {
			&::-moz-selection { background: $background; color: $color; text-shadow: none; }
			&::selection { background: $background; color: $color; text-shadow: none; }
		} @else {
			::-moz-selection { background: $background; color: $color; text-shadow: none; }
			::selection { background: $background; color: $color; text-shadow: none; }
		}
	}

## Developers

+ [Stijn Van Minnebruggen](http://donotfold.be)
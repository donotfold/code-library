# Peek-A-Boo Scroll

Elastic or bouncy scroll in browsers is fun, but you can't show content in the extra space.
By default, the extra space uses the background color from the HTML of your page.

But... here's a little CSS hack to show content above or below the body when scrolling!

## HTML code

Just place a div in your html:

	<div class="toppie"><img src="https://media.giphy.com/media/t6UCTJ2kRU7bG/giphy.gif" alt="" /></div>
	<div class="bottompie"><img src="https://orig00.deviantart.net/4c0d/f/2011/242/d/1/pink_feet_by_demordo01-d48drpi.gif" alt="" /></div>

## CSS Code

And use the following CSS to make it visible in the scrolling part:

	.toppie {
		position: absolute; top: 0; right: 0; left: 0; z-index: -1;
		height: 100%; transform: translate3d(0, -99.999%, 0);
	}
	.bottompie {
		position: fixed; bottom: 0; right: 0; left: 0; z-index: -1;
		height: 100%; transform: translate3d(0, 99.999%, 0);
	}

## How it works

The div's are placed absolute (or fixed for the bottom).
We added a z-index of -1 to make sure these div's won't mess up your site.
The height of the div is set to 100% and with the translate3d we place it above (or below) the visible area in your browser.

## Oh, eh...

You probably want to add the following code to your css to make sure your content is visible ;)

	display: flex;
	align-items: flex-end; /* or flex-start for the bottom shizzle */
	justify-content: center;

## Some 'need-to-knows'

There are a couple of important things you should know about these things:
+ the translate3d is necessary to make it work
+ the 99.999% too, because when it's completely out of view, gif's (or other animations) won't work
+ this code has been tested in Chrome and Safari on a Mac, and MSFT Edge on a PC

## Developers

+ [Stijn Van Minnebruggen](http://donotfold.be)
+ [Bram Verdyck](http://sobra.be)
+ [Sven Lemmens](http://laymoon.be)
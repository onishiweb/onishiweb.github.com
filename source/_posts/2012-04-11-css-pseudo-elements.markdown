---
layout: post
title: "CSS Pseudo-elements"
date: 2012-04-11 13:26
comments: false
categories: 
---

After reading an article by <a href="http://twitter.com/#!/anna_debenham">Anna Debenham</a> on the <a href="http://maban.co.uk/68">nth-of-type pseudo element</a> it got me thinking about a recent client site in which the :before and :after pseudo-elements came in extremely handy. So I thought I'd share with you quickly what I did and give you an example similar to Anna's of where pseudo-selectors can be very useful in responsive web development.

So the website in question is the <em>stunning</em> online store I built responsively for Sting and Trudie Styler's Tuscany wine, honey and olive oil; <a href="http://www.palagioproducts.com">www.palagioproducts.com</a>. This was pretty much the first responsive website that One had decided to build and so it was a bit of a challenge from the outset, but one element of the design became quite tricky, the element in question being the fancy borders that sit at the top and bottom of the website.

<img src="http://www.onishiweb.co.uk/wordpress/wp-content/uploads/2012/04/ll-palagio-border.jpg" alt="" title="ll-palagio-border" class="alignnone size-full wp-image-205" />

Now normally in a fixed width site these could be easily produced using an image in the background, however as this was a responsive site, we needed the borders and the edgings to adjust depending on the width of the viewport and still retain their proportions, and this is where :before and :after came in.

Here's how it was coded and an example on the page below (change the size of the browser and you should see the border expand and contract with the edging's staying in place at the left and right sides of the border).

<!-- Code example and demo -->

<div id="palagio-divider"></div>

<pre>
.divider
{
	clear: left;
	position: relative;
	width: 90%;
	height: 34px;
	margin: 0 5%;
	background: url(images/common/divider-background.png) top center no-repeat;
}

.divider:after
{
	content: "";
	width: 65px;
	height: 34px;
	display: block;
	background: url(images/common/divider-left.png) top left no-repeat;
	position: absolute;
	top: 0px;
	left: -6%;
}

.divider:before
{
	content: "";
	width: 65px;
	height: 34px;
	display: block;
	background: url(images/common/divider-right.png) top left no-repeat;
	position: absolute;
	top: 0px;
	right: -6%;
}
</pre>

So there you go, a really useful application of the :before and :after pseudo-elements for Responsive web development. Enjoy!
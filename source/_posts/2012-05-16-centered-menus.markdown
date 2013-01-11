---
layout: post
title: "Centered Menus"
date: 2012-05-16 15:49
comments: false
categories:
published: false
---

So a while ago I was tasked with the job of building the fantastic site that is now <a href="http://www.palagioproducts.com/">www.palagioproducts.com</a>. When I first saw the designs I was very happy that it would be a nice straight forward build and I would have no real issues. I've already posted about one of the hurdles I encountered building the site which was the <a title="CSS Pseudo-elements" href="http://www.onishiweb.co.uk/2012/04/css-pseudo-elements/">lovely responsive borders</a> using CSS pseudo elements, yet that wasn't the issue that most took me by surprise. The first major issue I encountered was a centrally aligned main menu, as seen here:

<a href="http://www.onishiweb.co.uk/wordpress/wp-content/uploads/2012/05/Il-Palagio-main-menu.png"><img class="alignnone size-full wp-image-263" title="Il Palagio main menu" src="http://www.onishiweb.co.uk/wordpress/wp-content/uploads/2012/05/Il-Palagio-main-menu.png" alt="" width="480" height="auto" /></a>

I'll be honest I was stumped, at first I thought I should be able to get it working with my already quite extensive knowledge of CSS but for the life of me I wasn't getting anywhere. I was very reluctant however to change any of my markup from the standard tidy navigation markup I've become accustomed to writing (below).
<pre><nav>
	<ul>
		<li><a href="#">Item 1</a></li>
		<li><a href="#">Item 2</a></li>
		<li><a href="#">Item 3</a></li>
	</ul>
</nav></pre>

So on the hunt I went for a solution as clearly I couldn't come across one myself.

And this is what I found, I know a couple of people who've had this issue recently as well and I'm sorry I'm only just posting this but you're going to kick yourself when you see the next couple of lines:

<pre>
nav ul {	
	width: 100%;	
	text-align: center;
	padding: 0;
}

nav ul li {	
	display: inline;	
}
</pre>

Here's what it produces:

<nav id="centered-nav">
<ul>
	<li><a href="#">Item 1</a></li>
	<li><a href="#">Item 2</a></li>
	<li><a href="#">Item 3</a></li>
</ul>
</nav>

And it really is as <strong>simple</strong> as that!
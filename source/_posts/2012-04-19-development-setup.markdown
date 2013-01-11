---
layout: post
title: "New development setup"
date: 2012-04-19 16:30
comments: false
categories: 
---

Recently at One we've been considering a more collaborative way of working and this has led to most of us looking at the tools we use and how we develop. In this post I just want to quickly run through how I've recently changed the way I work and what tools and technologies I've started to use.

<h2>My Mac setup</h2>

At home I use a 13" MacBook Pro and have found myself really enjoying using the multiple desktops and gestures on the trackpad more and more. So because of this in the office I now have removed my second monitor and am using the iMac in the same way as the MacBook at home, <del datetime="2012-04-19T16:16:02+00:00">all I need now is a trackpad at work (you never know they may buy me one if I ask nicely)</del> I asked nicely and now I do have one which is making it a lot smoother. 

I've found this style of setup really handy and it allows me to have some apps at full screen like my text editor and mail and then easily get between them with a simple four-finger swipe on the trackpad. At the office this also means I can put all my mail and twitter etc off on another desktop so I'm no longer distracted quite as often.

<h2>MAMP</h2>

Because we have recently moved to local development I've needed to set up a server environment on my Mac, I've tried both XAMP and MAMP but found the latter the easier to set up (although the issues I had with XAMP were probably more user related than software to be honest).

Also with the help of Clinton (<a href="http://twitter.com/iblamefish">@iblamefish</a>) I've set up my mac to give the development sites I'm working on local domains (in the form of http://mysite.dev), here's how I did it (which is basically how Clinton told me too but I thought I'd share it):

<ol>
	<li>First, personally I have set up a separate folder in the MAMP directory (/Applications/MAMP/sites/) to store all the local dev sites I'll be working on. You can of course just use the htdocs folder by default but having this folder setup separately means I can use htdocs for little jobs that I'm happy accessing via localhost/site</li>
	<li>Next edit the Apache config file at /Applications/MAMP/conf/apache/httpd.conf and uncomment the line which includes the "extra/httpd-vhosts.conf" file (line 525).</li>
	<li>Set up hosts for the site you're creating in /Applications/MAMP/config/apache/extra/httpd-vhosts.conf as below:
<pre>
<VirtualHost *:80>
	ServerName mysite.dev
	DocumentRoot /Applications/MAMP/sites/mysite.dev/
</VirtualHost>
</pre>
	</li>
	<li>Edit the local hosts file to tell your computer where mysite.dev is either logged in as superuser or via sudo (e.g. sudo vi /etc/hosts) and add in the line: 127.0.0.1	mysite.dev</li>
	<li>Restart Apache and then go to http://mysite.dev/ and you're done.</li>
</ol>

<h2>Sublime Text 2</h2>

I've only recently changed over to using Sublime Text 2 as my main editor and have found the transition fantastic and the tools available and excellent for how I code. Since I moved to a Mac from PC I've been using TextWrangler as it was a free editor and had SFTP (which for a long time in the office we've needed for all dev work). Since we've made the recent choice to move to local development it's been less important for me to have SFTP and therefore I've had more chance to trial Sublime and it's made life significantly easier. 

Sublime for me is a nice compromise to using Vim, it may not be quite as powerful but the learning curve for Vim for me was a bit too steep and became time consuming when trying to work on quick projects. Sublime also is very expandable with a vast array of plugins that I've been making good use of, here's a list of the plugins I have installed at the moment, most of which I found in <a href="http://net.tutsplus.com/tutorials/tools-and-tips/essential-sublime-text-2-plugins-and-extensions/">this article from Nettuts</a>:

<ul>
	<li><a href="http://wbond.net/sublime_packages/package_control">Package control</a> - install this first as it makes installing packages ridiculously easy</li>
	<li>SFTP</li>
	<li>Zen coding</li>
	<li>Git</li>
	<li>LESS</li>
	<li>Wordpress</li>
	<li>Search Wordpress codex</li>
	<li>jQuery functions</li>
	<li>Prefxr</li>
</ul>

<h2>LESS</h2>

Since the beginning of the year I've been interested in learning more about LESS and introducing it to my dev setup. I learned a lot of the basics thanks to a brilliant <a href="http://www.12devsofxmas.co.uk/2011/12/less/">tutorial on the 12 Devs of Xmas site by Anthony Killeen</a>, but I really wanted to be using it on a more frequent basis to be able to get the most out of it. Unfortunately as I'm a part of a development team this is not something I can simply choose to do without it being discussed first and getting the unanimous nod from both the development team and our directors. Fortunately though it was a fairly easy decision to make as we all agreed that by using LESS we could become more productive and efficient producing sites as a team and with that getting the go-ahead from the directors wasn't too hard.

So with the decision taken that we will where possible begin to develop in LESS I've began working on any new sites I build with LESS making use of things like the nested rules and variables etc. But what LESS has enabled us to do as a development team is to modularise our CSS into various mixins and build up a library of useful blocks of CSS that we can use on a variety of projects, at the moment what we have is fairly limited but over time as we build more and more in LESS we'll be able to grow the library as we continue to build new sites. 

<h2>Codekit</h2>

Of course working with LESS means that you need something to compile .less files into CSS. The LESS app is perfectly capable of this and I was initially using it when I started, however, a colleague pointed me towards Codekit (from the same people who make LESS.app) and I've found it to be much more powerful and makes your workflow so much smoother overall. The combination of LESS compiling, JS compile and concatenation, live browser reloading, and image optimisation all in one app is just mind-blowing! Also with functionality to compile SASS and Stylus files, Coffeescript and HAML/Jade it's extremely useful for any development setup you have.

My favourite part of Codekit though has to be the project and framework management. The ability to create frameworks of LESS files (as mentioned), store them in one central location and include them in all of my projects using Codekit is incredible. It means I have the power to create a series of update-able sets of code libraries, store them in one single place and have them update across all of my projects. 

Codekit's still in beta at the moment and plan to release at some point next month to the app store with I think about a $9.99 price tag which for the functionality you receive is worth every penny!

<h2>Git</h2>

Finally I just want to touch quickly on Git/Github. I've never been part of a big coding company so version control has never really come up, but because of the usefulness of Github and the ease of use of Git I thought that I'd better add it to my repository. So I'm still getting used to using it but so far for storing several things that I'm working on I've found Git quite easy to get along with and with the use of Github I've been able to share some of the things I've been doing with colleagues. If you want to check out what I've done so far head over to <a href="http://github.com/onishiweb">http://github.com/onishiweb</a> and take a look, but be warned there's really nothing that interesting over there at the moment.

So there we go, a brief look at the new setup I've been using and how it's helped make me a lot more efficient and productive, would be great to hear how it compares to yours or whether you have any advice for other tools that I might find useful, so please comment or drop me a tweet! Cheers.
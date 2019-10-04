Blocking Bad Bots in 3 Easy Steps with Lighttpd.
================================================

I figured that a good follow up to my last post would be a new one about
good bot stopping practices. In this tutorial, we’ll be looking…

------------------------------------------------------------------------

### Blocking Bad Bots in 3 Easy Steps with Lighttpd.

I figured that a good follow up to my
<a href="http://blog.ctis.me/2015/04/catching-spam-bots-with-node.html" class="markup--anchor markup--p-anchor">last post</a>
would be a new one about good bot stopping practices.  
   
 In this tutorial, we’ll be looking at best practices for Lighttpd, but
configuration options for these tips are available in all major web
servers (Apache, Nginx, IIS, etc).  
   
 The internet is a scary place, and anyone whose even taken a cursory
glance at their web server access logs will certainly have noticed the
amount of clearly malicious or spammy requests made to their web server.
Internet scrapers and spam referrers are just some of the nasty things
you’re sure to see strewn about your access logs.  
   
 These bots are typically searching for exploits (which is an automated,
brute-forced process), though many others are looking for personal
information such as email addresses and phone numbers to send spam to.
There may also be search engines who crawl your site too frequently,
making large amounts of requests at close intervals (eating bandwidth
and system resources).  
   
 There are a few ways to keep this behavior under control, at least for
the good robots. Any good webmaster will have undoubtedly created a
good, strong robots.txt to keep out unwanted crawlers, but a shockingly
large amount of them disregard it entirely.  
   
 A good example of this is Baidu, who, after being blocked in both my
robots.txt and my web server configuration, actually went so far as to
change the user agent of their web spiders to circumvent the blocks!  
   
 Because such nasty programs exist, we have to “break out the big guns”
and block them in our web server config, and thankfully, Lighttpd
provides plenty of options for us to do just that :)  
   
 **Step one.**  
 **  
** Grab the latest copy of
<a href="https://github.com/ctrezevant/everlasting-botstopper" class="markup--anchor markup--p-anchor">my anti-spam configuration</a>
and copy it to your clipboard.  
   
 **Step two.**  
 **  
** On your server, cd to /etc/lighttpd and touch the file spam.conf.
Open that file in your favorite text editor and paste in the contents of
the anti-spam config. *(note: you may need to su to root or use sudo to
create and edit these files)*  
   
 Open your lighttpd configuration file (usually
/etc/lighttpd/lighttpd.conf) and add the line:  
   
 include spam.conf  
   
 **Step three.**  
 **  
** Reload your web server’s configuration, and restart it:  
   
 /etc/init.d/lighttpd reload  
 /etc/init.d/lighttpd restart  
   
 And just like that, a large portion of the most common offenders is
blocked from your site!  
   
 Of course, this tutorial wouldn’t be complete without a section on how
to add your own custom rules, so I’ll explain that, too!  
   
 Let’s look at the three different conditional statements that you would
be using to block bots and referrers from accessing your site. They are
more or less self-explanatory, so here they are:

1.  <span id="c017">$HTTP\[“referer”\]</span>
2.  <span id="02a2">$HTTP\[“useragent”\]</span>
3.  <span id="7de7">$HTTP\[“remoteip”\]</span>

These conditionals, when used in conjunction with
<a href="http://redmine.lighttpd.net/projects/1/wiki/docs_configuration#Conditional-Configuration" class="markup--anchor markup--p-anchor">one of lighttpd’s conditional operators</a>
and
<a href="https://en.wikipedia.org/wiki/Regular_expression" class="markup--anchor markup--p-anchor">regular expressions</a>
give you powerful, granular control over who (or what) can access your
site.

------------------------------------------------------------------------

*Originally published at*
<a href="http://blog.ctis.me/2015/05/blocking-bad-bots-in-3-easy-steps-in.html" class="markup--anchor markup--p-anchor"><em>blog.ctis.me</em></a>
*on May 11, 2015.*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [May 11, 2015](https://medium.com/p/434f8c276f24).

<a href="https://medium.com/@charltontrez/blocking-bad-bots-in-3-easy-steps-with-lighttpd-434f8c276f24" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

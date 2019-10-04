The LLMN Stack: A Comparison
============================

I figured I should make a short post about my web stack.

------------------------------------------------------------------------

### The LLMN Stack: A Comparison

<figure>
<img src="https://cdn-images-1.medium.com/max/600/0*Fz8JKky8cLV2xGJc.jpg" class="graf-image" alt="" /><figcaption><em>Artist’s representation of the LLMN stack.</em></figcaption>
</figure>

I figured I should make a short post about my web stack.

### A bit of background

I prefer lightweight and fast pieces of software that sip system
resources, so it’s no secret that I dearly love web servers like
Lighttpd and NodeJS. Coming from a background where old, slow, and
obsolete hardware was all that I had available to play around with put
system optimization at the forefront of my priorities.  
   
 My very first “server” of sorts was an original raspberry pi model B. I
kept it in a cabinet in my room, and it was connected to my network via
wi-fi. Reception was terrible, and so the website I ran on it (which was
hosted by Apache) was sluggish but still *just* good enough that I was
able to serve a 144p shockwave flash video of my principal dancing
hilariously to some music, which was super funny among my peers.  
   
 Eventually, I switched from Apache to Lighttpd, because I was also
trying to use the pi as a media center with XBMC and a Samba server, and
I needed a lighter weight web server (and besides, for completely static
sites Apache is overkill).  
   
 In my searching, I came across Lighttpd (I don’t know why I didn’t find
Nginx first, but I wish I had, especially since Lighty v1.5 is slow in
coming) and it solved all of my problems. I would later switch back to
Apache when I got a slightly nicer desktop from a computer recycling
plant, but I eventually returned, once again, to Lighttpd.

### About the stack

So, with speed, a small footprint, and performance in mind, LLMN is
extremely close to
<a href="https://lemp.io/" class="markup--anchor markup--p-anchor">LEMP</a>.
In fact, in benchmarks, Lighttpd and Nginx are remarkably close (though
Nginx is often slightly faster).  
   
 Here are a few good benchmarks comparing them:  
 As noted earlier, the performance of the two servers is strikingly
similar. That said, for my needs (running a small site that averages
around 1k requests per day), Lighttpd is perfect. It’s been rock solid,
low-maintenance, and has gracefully scaled up to my needs as they have
grown, and hasn’t crashed once over years and years of use. *I will
admit, however, that I’ve been considering switching to Nginx recently,
though I dread porting my configuration files. Incidentally, that would
make this a LEMN stack :P*  
   
 In fact, I was DDOSed several months ago, and my uplink bandwidth was
saturated long before Lighttpd even began to use more than 2% CPU
usage.  
   
 Besides the web servers, the other major difference between these two
stacks is the choice of server-side language (which, in the case of
LLMN, is JavaScript instead of PHP).  
   
 There are a few good reasons for this:  
   
 **I love JavaScript.** It’s the language of the web and
<a href="http://githut.info/" class="markup--anchor markup--p-anchor">has absolutely soared in popularity</a>
over the past few years. It runs everywhere, from desktops and mobile
devices to servers and
<a href="https://tessel.io/" class="markup--anchor markup--p-anchor"><em>even</em></a>
<a href="http://www.espruino.com/" class="markup--anchor markup--p-anchor"><em>microcontrollers</em></a>*!*
The ability to develop and maintain applications in a single language
across both the client and server is also very alluring, and simplifies
the development process considerably.  
   
 **NodeJS, like Lighttpd, is fast, lightweight, and asynchronous**. Have
a look at
<a href="http://www.hostingadvice.com/blog/comparing-node-js-vs-php-performance/" class="markup--anchor markup--p-anchor">this benchmark</a>.
Or
<a href="http://blog.prahladyeri.com/2014/06/php-vs-node-js-real-statistics.html" class="markup--anchor markup--p-anchor">this test</a>.  
   
 **NodeJS has lots of modules, packages, and libraries available to
freely use** (though this is also true of PHP). There are over 153,000
packages available on npm, which is Node’s package manager.  
   
 **NodeJS has an enormous community.** Because JavaScript runs
everywhere, Node developers can get help from the entire JavaScript
community, while working on a project. This portability means that help
and support is extremely easy to come by. As a result, Node is great for
newcomers to server-side web development.  
   
 Also,
<a href="https://nodejs.org/industry/" class="markup--anchor markup--p-anchor">these fortune 500 companies</a>
all use Node for their backend.

### Conclusion

-   <span id="6f1e">LLMN is fast, low-maintenance, and extremely
    resilient, with an incredibly small footprint.</span>
-   <span id="33cb">NodeJS is fast, has a great community, and highly
    extensible with lots and lots of modules and libraries. JS as a
    common language on both the client and server makes web development
    much easier.</span>
-   <span id="4d0b">NodeJS still isn’t as widely used as PHP, which
    powers popular frameworks like Wordpress.</span>
-   <span id="683e">While Lighttpd is fantastic for static pages or as a
    proxy, Apache, though heavier, is generally better at interfacing
    with PHP and serving dynamic content. Lighttpd is also outperformed
    by Nginx by a hair. Compared to Nginx, Lighttpd lacks some
    features.</span>

------------------------------------------------------------------------

*Originally published at*
<a href="http://blog.ctis.me/2015/06/the-llmn-stack.html" class="markup--anchor markup--p-anchor"><em>blog.ctis.me</em></a>
*on June 2, 2015.*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [June 2, 2015](https://medium.com/p/e12f6b8185d3).

<a href="https://medium.com/@charltontrez/the-llmn-stack-a-comparison-e12f6b8185d3" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

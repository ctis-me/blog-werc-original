Build a simple IP echo service with Lighttpd and mod\_magnet
============================================================

A delightful 5 minute project

------------------------------------------------------------------------

### Build a simple IP echo service with Lighttpd and mod\_magnet

#### A delightful 5 minute project

<figure>
<img src="https://cdn-images-1.medium.com/max/800/1*p7baajYwagRgpZWqPZlDyA.jpeg" class="graf-image" alt="" /><figcaption>Before you can jam with the console cowboys in Cyberspace, you’ll need to know your IP address.</figcaption>
</figure>

Assuming you’ve done most any work in the tech space, you’ve undoubtedly
come across the myriad of free services that will tell you your external
IP address. These are especially useful for a number of reasons, with
some examples including checking whether a VPN connection is working
correctly, configuring DNS records, and determining whether traffic on
your network is NATed.

Now, there are many providers of this service (with
<a href="https://whatismyip.com" class="markup--anchor markup--p-anchor">whatismyip.com</a>
and
<a href="https://www.technorms.com/6953/find-ip-address-with-google-search" class="markup--anchor markup--p-anchor">Google’s own service</a>
being among the most popular), but they’re often plastered with ads and
tracking, somewhat slow, and worst of all- difficult for scripts to
parse! Wouldn’t it be better to have a simple solution available that
you can host yourself?

As it happens, this problem is very easy to solve using the
<a href="https://redmine.lighttpd.net/projects/lighttpd/wiki/AbsoLUAtion" class="markup--anchor markup--p-anchor">mod_magnet</a>
component of
<a href="https://www.lighttpd.net/" class="markup--anchor markup--p-anchor">Lighttpd</a>
web server. So, as part of this post, I’ll assume you’re at least
passively familiar with Lighttpd, the fact that Lighttpd can load
modules, and very basic HTTP transactions. If not, it’s OK! I’ve done my
best to break it all down for you.

#### What is mod\_magnet?

Mod\_magnet is a module available for Lighttpd which exposes a powerful
interface for extending Lighttpd’s request handling using the
<a href="https://www.lua.org/about.html" class="markup--anchor markup--p-anchor">Lua language</a>,
providing the user a much higher degree of customizability than that
found in Lighttpd’s built-in routing facilities. Essentially,
mod\_magnet is a means of running your own custom Lua scripts on HTTP
requests, in place of Lighttpd.

#### Setting it up

Whether or not all of this above sounds like a steaming pile of jargon
matters very little, because the technical nitty-gritty of mod\_magnet
is far beyond the scope of this post. I’m also not a fan of just telling
people where to paste things, so we’ll instead focus on breaking down
the very simple 3-line Lua script I’ve put together for this purpose,
along with the tiny snippet of Lighttpd configuration that makes it all
run:

Here’s what happens in that 3 line script:

1.  <span id="dfea">We fill the server’s response content with the
    client’s IP address, which we read from the script’s
    <a href="https://redmine.lighttpd.net/projects/1/wiki/Docs_ModMagnet#lightyenv" class="markup--anchor markup--li-anchor">environment variables</a>.</span>
2.  <span id="d440">We make sure that the MIME type of the response is
    set to text/html, because we’re just nice people.</span>
3.  <span id="7fef">We return a \`200 OK\` status code with the
    response .</span>

And, in that 6-line Lighttpd configuration:

1.  <span id="5128">We load the mod\_magnet module (if it isn’t already
    loaded, otherwise you should comment this out).</span>
2.  <span id="beb4">We create a
    <a href="https://www.cyberciti.biz/faq/howto-lighttpd-virtualhost-configuration/" class="markup--anchor markup--li-anchor">virtual host</a>
    (my hostname is
    <a href="http://ip.ctis.me" class="markup--anchor markup--li-anchor">ip.ctis.me</a>,
    though you can use any domain you control, or even a custom path
    \[e.g. yoursite.com/ip\]).</span>
3.  <span id="c60a">We give the mod\_magnet module the path to the Lua
    script it should run when this particular host recieves a
    request.</span>
4.  <span id="1475">We set the document root of this vhost to wherever
    you’ve put the Lua script *(update 3 and 4 accordingly, of
    course)*.</span>
5.  <span id="c4ab">Set the access log to /dev/null because I don’t care
    to keep logs about this particular endpoint.</span>

So, to set it all up, all you really have to do is put the .lua file in
your web root somewhere, and then updating your Lighttpd configuration
accordingly using my template as a guide. Simple, isn’t it?

As per usual, a live example of this in action can be found
<a href="http://ip.ctis.me" class="markup--anchor markup--p-anchor">here</a>.

*Enjoy!*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [July 5, 2017](https://medium.com/p/d2722d4bff76).

<a href="https://medium.com/@charltontrez/build-a-simple-ip-echo-service-with-lighttpd-and-mod-magnet-d2722d4bff76" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

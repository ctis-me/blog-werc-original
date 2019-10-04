Cooling Down the Hotlinks: Taming Bandwidth Usage with No Compromises
=====================================================================

Last year, I noticed an alarming increase in the outbound traffic on
charltontrezevant.com: I was serving nearly 5GB of photos per day. For…

------------------------------------------------------------------------

### Cooling Down the Hotlinks: Taming Bandwidth Usage with No Compromises

> [](https://twitter.com/charltontrez/status/655440325390049280)

Last year, I noticed an alarming increase in the outbound traffic on
<a href="http://charltontrezevant.com/" class="markup--anchor markup--p-anchor">charltontrezevant.com</a>:
I was serving nearly 5GB of photos *per day*. For a static site with
&lt;500 page views per week, it was immediately apparent that something
had gone terribly wrong.  
   
 As it turns out, I had been receiving enormous amounts of traffic from
internet forums that had been hotlinking images from my site, most of
which were from the weed page.  
   
 Luckily, it was incredibly easy to put a stop to this. Returning once
again to the powerful sorcery of Lighttpd, we can easily reject certain
types of traffic (In this case, images requested from domains other than
mine) while allowing legitimate requests to pass through:

*Note that this snippet allows certain referrers and user-agents through
(such as Googlebot, Skype Web Preview, etc) so that legitimate uses are
enabled.*  
   
 This snippet will redirect all requests from invalid domains to
<a href="https://i.imgur.com/yijpex7.png" class="markup--anchor markup--p-anchor">this image</a>,
thus returning my bandwidth stats to sane levels while also expressing
my mild irritation.  
   
 The
<a href="https://imgur.com/a/3thYQ" class="markup--anchor markup--p-anchor">aftermath</a>
scattered my face across the net, which was incredibly funny.

------------------------------------------------------------------------

*Originally published at*
<a href="http://blog.ctis.me/2016/01/cooling-down-hotlinks-taming-bandwidth.html" class="markup--anchor markup--p-anchor"><em>blog.ctis.me</em></a>
*on January 18, 2016.*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [January 18, 2016](https://medium.com/p/8b23d08c4db6).

<a href="https://medium.com/@charltontrez/cooling-down-the-hotlinks-taming-bandwidth-usage-with-no-compromises-8b23d08c4db6" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

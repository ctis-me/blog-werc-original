Scraping for Cache, Or: It’s Not Piracy If You Left It Out In The Open
======================================================================

Proudly included in the Spring 2016 edition of 2600 magazine!

------------------------------------------------------------------------

### Scraping for Cache, Or: It’s Not Piracy If You Left It Out In The Open

<figure>
<img src="https://cdn-images-1.medium.com/max/600/0*NLLp0JkGXq-LVIib.jpg" class="graf-image" alt="" />
</figure>

***Proudly included in the***
<a href="https://www.2600index.info/article.php?i=176&amp;a=2604&amp;o=" class="markup--anchor markup--p-anchor"><strong><em>Spring 2016 edition</em></strong></a>
***of 2600 magazine!***

As a student, I love to have digital copies of my textbooks available.
Ease of reference, portability, and minimal back strain are 3 reasons
why finding digital copies of my books are hugely important to me.
Therefore, I’m understandably annoyed when textbooks, especially ones
that are several years old, can’t be found online, or are available in
online stores at exorbitant prices. Absolute madness!

A recent example of this heinous lack of electronic books would be my
APUSH textbook. It isn’t terribly old, in fact, it was published in
2012, and an online edition is available from McGraw Hill. In theory, an
online edition should mean the end of my accessibility problem (and back
pain), however, in order to access the online edition, I’d an access
code from my school, something that they had not and could not provide
to me. With all legitimate means of digital access exhausted, I would
have to resort to other methods of enabling my laziness…

#### Enter Google.

As Google’s web spiders crawl the web, they not only index web pages,
but they also cache copies of pages, usually for a month or so, during
which Google will host its own copy of the resource. In practice, this
means that there’s often a good chance that content on the web that has
been deleted by a site owner is retrievable, so long as it has been
indexed by Google. In fact, there are several organizations that exist
to do exactly this sort of thing, most notably
<a href="http://web.archive.org/" class="markup--anchor markup--p-anchor">Archive.org</a>,
though Google is usually better about getting into the smaller cracks
and crevices of the internet where my books are more likely to be
stored.

#### Research.

To start off my search, I searched for exact strings taken out of my
textbook, which usually leads to a PDF scan of a section that’s clear
enough for google to run OCR. What I found, however, was something much,
much better: Google had indexed pages directly from McGraw Hill’s
development servers, with cached copies that spanned the entire book!

And not only my APUSH textbook, but many, many others as well:

<figure>
<img src="https://cdn-images-1.medium.com/max/800/0*WMOdvNQTKkVhu5IZ.png" class="graf-image" alt="" />
</figure>

A few quick observations for each URL led me to a way to
programmatically download the book:

-   <span id="c6ae">Each URL followed the same format,
    <a href="http://dev6.mhhe.com/textflowdev/genhtml/%3CISBN%3E/%3Cchapter%3E.%3Csection%3E.htm" class="markup--anchor markup--li-anchor">http://dev6.mhhe.com/textflowdev/genhtml/&lt;ISBN&gt;/&lt;chapter&gt;.&lt;section&gt;.htm</a></span>
-   <span id="556f">Cached versions of webpages could be easily
    retrieved from Google with the following URI format:
    <a href="https://webcache.googleusercontent.com/search?q=cache:%3Cfull" class="markup--anchor markup--li-anchor">https://webcache.googleusercontent.com/search?q=cache:&lt;full</a>
    URL of resource&gt;.</span>
-   <span id="2d37">My book has no more than 32 chapters, with no more
    than 7 sections per chapter, which means there are 224 pages to
    potentially retrieve in total.</span>

#### The Script.

That said, I whipped up the following script, which, though simple, was
able to completely retrieve my textbook from Google’s cache *and*
compile all of the downloaded HTML files into a single PDF:

Which left me with a complete, text-only copy of my book! Excellent!

*\*Note: The book has since been removed from Google’s cache, rendering
the script unusable in its current state.*

#### So, what have we learned?

As a company dealing in an industry where piracy is a major concern,
McGraw Hill should take extra precaution to ensure that all of its
content, especially content that they’re keen to monetize, is kept
strictly under their control. This means securing any channel where this
content could be exposed, which, in this case, was their dev servers.
Even when a resource is deleted from a site, there are usually cached
copies available *somewhere,* and once it’s out on the web, it’s out of
your control.

Another thing that webmasters can gather from this is that all web
content you host, even content hidden under several layers of
obfuscation, may as well be considered wide open to the web unless some
kind of authentication is implemented. If it exists on your server,
accessible to anyone, then anyone will access it.

With the above in mind, I hope that you’ve learned something about
keeping your content, and channels that lead to your content, in check
and under your control.

Happy hacking!

------------------------------------------------------------------------

*Originally published at*
<a href="http://blog.ctis.me/2016/04/scraping-for-cache-or-its-not-piracy-if.html" class="markup--anchor markup--p-anchor"><em>blog.ctis.me</em></a>
*on April 10, 2016.*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [April 10, 2016](https://medium.com/p/4025c037ba53).

<a href="https://medium.com/@charltontrez/scraping-for-cache-or-its-not-piracy-if-you-left-it-out-in-the-open-4025c037ba53" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

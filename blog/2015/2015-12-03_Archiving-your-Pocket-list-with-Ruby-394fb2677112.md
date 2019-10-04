Archiving your Pocket list with Ruby
====================================

I’ve been seeking a more powerful and extensible alternative to Bash,
and so I’ve recently begun experimenting with Ruby. For my first…

------------------------------------------------------------------------

### Archiving your Pocket list with Ruby

<figure>
<img src="https://cdn-images-1.medium.com/max/600/0*kG-1WsgX-W4WMEal.png" class="graf-image" alt="" />
</figure>

I’ve been seeking a more powerful and extensible alternative to Bash,
and so I’ve recently begun experimenting with Ruby. For my first “real”
test of the language, I decided to solve a problem I had been seeking an
answer to for some time: Since the web is constantly changing, how could
I go through my entire reading list and ensure that I had backup copies
of the articles I’ve saved? As it turns out, there was a fairly simple
solution to this-
<a href="https://gist.github.com/ctrezevant/a9cdcd617b1016b2351f" class="markup--anchor markup--p-anchor">only 35 lines of Ruby</a>!

The script itself uses the
<a href="https://github.com/taf2/curb" class="markup--anchor markup--p-anchor">Curb</a>
and
<a href="http://www.nokogiri.org/" class="markup--anchor markup--p-anchor">Nokogiri</a>
libraries to follow URL shorteners and parse HTML to ensure that the
third main component,
<a href="http://wkhtmltopdf.org/" class="markup--anchor markup--p-anchor">wkhtmltopdf</a>
(a personal favorite of mine), gets the most correct data for each link.
To get your Pocket data into the script, you simply use Pocket’s nifty
<a href="https://getpocket.com/export" class="markup--anchor markup--p-anchor">HTML export</a>
tool to get a webpage full of links to all of your saved articles.

Using the script is extraordinarily simple: Once dependencies are
installed (see the top of the script for more information on that), you
simply run

> ruby pocket\_export.rb ~/Downloads/ril\_export.html

and you’re off! The script creates the directory pocket\_export\_data to
store the PDFs it generates and pocket\_export\_errors.log to keep track
of any links it has trouble with.

Enjoy!

------------------------------------------------------------------------

*Originally published at*
<a href="http://blog.ctis.me/2015/12/archiving-your-pocket-articles-with-ruby.html" class="markup--anchor markup--p-anchor"><em>blog.ctis.me</em></a>
*on December 3, 2015.*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [December 3, 2015](https://medium.com/p/394fb2677112).

<a href="https://medium.com/@charltontrez/archiving-your-pocket-list-with-ruby-394fb2677112" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

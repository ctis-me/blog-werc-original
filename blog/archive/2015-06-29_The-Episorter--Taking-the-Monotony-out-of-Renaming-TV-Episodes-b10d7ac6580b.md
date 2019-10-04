The Episorter: Taking the Monotony out of Renaming TV Episodes
==============================================================

I recently had to rename around 200 TV episodes on my Plex server, a
daunting task that would normally involve several terribly boring…

------------------------------------------------------------------------

### The Episorter: Taking the Monotony out of Renaming TV Episodes

I recently had to rename around 200 TV episodes on my Plex server, a
daunting task that would normally involve several terribly boring hours
and hundreds of mv’s. That is, if I hadn’t taken advantage of the power
of Bash to solve my problem!

<a href="http://www.plex.tv/" class="markup--anchor markup--p-anchor">Plex</a>
is an absolutely amazing media server, and, when presented with a
directory full of media files, it’s generally able to match and
categorize them accurately and without human intervention. However, it
can be picky, especially when it comes to TV episodes. In my case, I had
a couple hundred episodes of The Office that followed a naming
convention that Plex didn’t like, meaning that I got all the way to
season 3 without realizing that I was missing nearly 10 episodes per
season!

My episodes were named like so:

…/plex/TV/The Office/Season 2/Episode 3 — Office Olympics.mp4

However, this is Plex’s preferred naming scheme:

…/plex/TV/The Office/Season 2/S02E3 — Office Olympics.mp4

As a result, I whipped up a small script to save me from a future of
bloodshot eyes and cramped hands, which was able to tear through the job
in less than 2 minutes in total:

I call it the episorter, and it takes all the variables that it requires
from the directory name (i.e. ‘Season 2’) and the number of episodes in
the current directory, and then renames each of the episodes to align
with Plex’s preferred scheme.  
   
 I hope it helps somebody!

------------------------------------------------------------------------

*Originally published at*
<a href="http://blog.ctis.me/2015/06/the-episorter-taking-monotony-out-of.html" class="markup--anchor markup--p-anchor"><em>blog.ctis.me</em></a>
*on June 29, 2015.*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [June 29, 2015](https://medium.com/p/b10d7ac6580b).

<a href="https://medium.com/@charltontrez/the-episorter-taking-the-monotony-out-of-renaming-tv-episodes-b10d7ac6580b" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

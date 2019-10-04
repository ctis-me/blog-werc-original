Language Speeds: A Quick and Dirty Test
=======================================

Some time ago I decided to run a quick test to determine the performance
of several popular programming languages by measuring the…

------------------------------------------------------------------------

### Language Speeds: A Quick and Dirty Test

<figure>
<img src="https://cdn-images-1.medium.com/max/600/0*Dur4T2Ctx5O5_rhg.jpg" class="graf-image" alt="" />
</figure>

Some time ago I decided to run a quick test to determine the performance
of several popular programming languages by measuring the execution time
of an algorithm to compute the greatest prime factor of a number.

The test itself was easy enough to set up and run, being no more than an
implementation of a simple algorithm in several languages combined with
a bash script to run them all in sequence. My findings, however, were
interesting.

I tested the following languages on several systems I had handy:

-   <span id="4ba7">C</span>
-   <span id="7010">Java</span>
-   <span id="4847">Python</span>
-   <span id="d40f">Ruby</span>
-   <span id="e97e">JavaScript</span>

Unsurprisingly, C won out for speed; its execution times were the lowest
across the board due to it being compiled directly to assembly.  
   
 In second place, surprisingly, came JavaScript. Looks like V8 really
*is* all it’s cracked up to be.  
   
 Following that, Python and Ruby were fairly close in speed, and Java
was slowest across the board.  
   
 I encourage you to run your own tests and post the results! The source
code (along with my initial test) is
<a href="https://github.com/ctrezevant/language-speedtests" class="markup--anchor markup--p-anchor">on GitHub.</a>

------------------------------------------------------------------------

*Originally published at*
<a href="http://blog.ctis.me/2015/11/language-speeds-quick-and-dirty-test.html" class="markup--anchor markup--p-anchor"><em>blog.ctis.me</em></a>
*on November 17, 2015.*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [November 17, 2015](https://medium.com/p/810ceb78fc77).

<a href="https://medium.com/@charltontrez/language-speeds-a-quick-and-dirty-test-810ceb78fc77" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

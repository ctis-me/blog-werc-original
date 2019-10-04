Get notified when your linux server boots.
==========================================

Getting notified of things is great, and when one of your servers boots
up, it’s always good to know when. With that in mind, it’s easy to…

------------------------------------------------------------------------

### Get notified when your linux server boots.

<figure>
<img src="https://cdn-images-1.medium.com/max/800/0*pLL42qQmpPHoQtOK.jpg" class="graf-image" alt="" />
</figure>

Getting notified of things is great, and when one of your servers boots
up, it’s always good to know when. With that in mind, it’s easy to add
this feature to most any Linux or BSD server without much trouble,
especially since I’ve already done the work for you :)

Here’s an example message, from one of my servers:

> *Box has booted!*

> *System information:*

> *Date and time:*

> *Thu Jul 9 20:43:49 EDT 2015*

> *Uptime (length of boot):*

> *20:43:49 up 1 min, 0 users, load average: 2.94, 0.98, 0.35*

> *Network addresses:*

> *LAN: 192.168.0.12   
> WAN: 93.184.216.34*

> *Server disk usage:*

> *Filesystem Size Used Avail Use%*

> *Mounted on/dev/mapper/Box — vg-root 1.8T 1.5T 266G 85% /*

By pasting my
<a href="https://gist.github.com/ctrezevant/850effec75aa2e0a92fa" class="markup--anchor markup--p-anchor">Boot Notification Script</a>
into your /etc/rc.local, you can use your local mail server to send boot
notifications with useful statistics whenever your system comes up, with
minimal and straightforward configuration.  
   
Note that this script requires a functioning mail server to be running
on the system (such as
<a href="https://en.wikipedia.org/wiki/Postfix_%28software%29" class="markup--anchor markup--p-anchor">Postfix</a>),
as well as the
<a href="https://en.wikipedia.org/wiki/Mailx" class="markup--anchor markup--p-anchor">mailx utility</a>,
which can be installed from the mailutils or bsd-mailx packages. In a
future post, I’ll explain how you can easily send mail via postfix using
Gmail as a relay, while also keeping your domain name intact.

For inital setup, which will produce the message shown above, you only
have to set 2 variables, EMAIL and LANIFACE. There is a third variable,
HOST, which is automatically set using the machine’s hostname.  
   
**EMAIL** should contain the email address to which messages should be
sent. If you like, you can add multiple addresses, separated by commas.
This can be any email address, including
<a href="http://goo.gl/hhAABm" class="markup--anchor markup--p-anchor">your phone’s</a>
if you’d like to get notifications via SMS.  
   
The second is **HOST**. This is set automatically from the machines
hostname and requires no manual configuration.  
   
The third is **LANIFACE**, which is the network interface that the LAN
IP should be retrieved from. Usually, this is eth0, but it changes
depending on your OS. You can run the command ip link show to get a list
of your available network interfaces, if you’re unsure.

*\*\*Note: On some systems, /sbin/ifconfig is not installed. This
command is usually replaced with /sbin/ip, with addresses shown using
the command “ip addr”.*

*Should this be the case, replace the code on line 52 with the
following:  
 \`/bin/ip addr | /bin/grep inet | /usr/bin/tail -n 2 | /usr/bin/head -n
1\`*

*Which should produce something along the lines of:  
 inet 192.168.0.12/24 brd 10.0.1.255 scope global eth0*

------------------------------------------------------------------------

*Originally published at*
<a href="http://blog.ctis.me/2015/07/get-notified-when-your-linux-server.html" class="markup--anchor markup--p-anchor"><em>blog.ctis.me</em></a>
*on July 23, 2015.*

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [July 23, 2015](https://medium.com/p/ba0fc9223064).

<a href="https://medium.com/@charltontrez/get-notified-when-your-linux-server-boots-ba0fc9223064" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

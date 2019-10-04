SDR Presentation
================

I gave a short presentation on SDR at the Hack@UCF meeting today. If
that piqued your interest and you’re ready to dive in, here are…

------------------------------------------------------------------------

### SDR Presentation

I gave a short presentation on SDR at the Hack@UCF meeting today. If
that piqued your interest and you’re ready to dive in, here are
supplemental materials and some cool links that will get you started
down the radio rabbit hole.

### Slides

### Demos

### Sweet Links

-   <span
    id="f15e"><a href="http://websdr.org/" class="markup--anchor markup--li-anchor">http://websdr.org/</a></span>

Want to start scanning the airwaves, but you don’t have any hardware
yet? Hundreds of universities and hobbyist clubs have you covered! This
site will link you up to hundreds of different receivers around the
world, which you can listen to and control free of charge.

-   <span
    id="a5b5"><a href="https://www.fcc.gov/oet/ea/fccid" class="markup--anchor markup--li-anchor">https://www.fcc.gov/oet/ea/fccid</a>
    (or
    <a href="https://fccid.io/" class="markup--anchor markup--li-anchor">https://fccid.io/</a>)</span>

Any products sold in the US that let off radio waves have to be tested
and registered with the FCC. When this happens, the FCC assigns an ID to
the product, which is usually on the exterior somewhere. You can look
this ID up at either of the sites above to find a wealth of information,
including the frequencies it uses.
<a href="https://fccid.io/WQJ-IDCL-51" class="markup--anchor markup--p-anchor">Here’s an example</a>.

-   <span
    id="91bf"><a href="https://www.reddit.com/r/RTLSDR/" class="markup--anchor markup--li-anchor">/r/RTLSDR</a></span>

A great community of SDR & radio enthusiasts. Be sure to check out
<a href="https://www.reddit.com/r/RTLSDR/wiki/index" class="markup--anchor markup--p-anchor">the wiki</a>!

### More Sweet Demos

-   <span
    id="acaa"><a href="https://www.youtube.com/watch?v=LZAJM8ZlfvY" class="markup--anchor markup--li-anchor">Balint Seeber: Hacking the Wireless World with SDR</a>
    (<a href="https://www.blackhat.com/docs/asia-15/materials/asia-15-Seeber-Hacking-the-Wireless-World-With-Software-Defined-Radio-2.0.pdf" class="markup--anchor markup--li-anchor">slides</a>)</span>
-   <span
    id="8445"><a href="http://samy.pl/opensesame/" class="markup--anchor markup--li-anchor">Samy Kamkar’s Opensesame project, which can open any garage door</a>
    (Samy is my hero)</span>
-   <span
    id="7d05"><a href="http://blog.cyberexplorer.me/2014/01/sniffing-and-decoding-nrf24l01-and.html" class="markup--anchor markup--li-anchor">Sniffing/Decoding Bluetooth LE</a></span>
-   <span
    id="0a05"><a href="https://nickwhyte.com/post/2017/reversing-433mhz-raex-motorised-rf-blinds/" class="markup--anchor markup--li-anchor">Analyzing captured packets from a remote to reverse-engineer automatic window blinds</a></span>
-   <span
    id="9c53"><a href="https://discourse.criticalengineering.org/t/howto-gsm-base-station-with-the-beaglebone-black-debian-gnu-linux-and-a-usrp/56" class="markup--anchor markup--li-anchor">Building a GSM base station with a BeagleBone, OpenBTS, and a USRP</a></span>
-   <span
    id="d9b0"><a href="https://www.rtl-sdr.com/reverse-engineering-signals-universal-radio-hacker-software/" class="markup--anchor markup--li-anchor">Reverse Engineering Signals with the Universal Radio Hacker Software</a></span>

### Getting Started

Recommended reading:

-   <span
    id="5e2a"><a href="https://www.reddit.com/r/RTLSDR/wiki/guides" class="markup--anchor markup--li-anchor">https://www.reddit.com/r/RTLSDR/wiki/guides</a></span>
-   <span
    id="2b62"><a href="https://www.reddit.com/r/RTLSDR/wiki/index" class="markup--anchor markup--li-anchor">https://www.reddit.com/r/RTLSDR/wiki/index</a></span>
-   <span
    id="7f0a"><a href="http://rtlsdr.org/#history_and_discovery_of_rtlsdr" class="markup--anchor markup--li-anchor">History of RTLSDR</a></span>
-   <span
    id="c2b6"><a href="https://osmocom.org/projects/sdr/wiki/rtl-sdr" class="markup--anchor markup--li-anchor">Technical Background</a></span>

### Software

-   <span
    id="0c80"><a href="https://github.com/antirez/dump1090" class="markup--anchor markup--li-anchor">https://github.com/antirez/dump1090</a></span>

This is the dump1090 project, which was one of the pieces of software I
demoed. Using your SDR dongle, dump1090 receives the
<a href="https://en.wikipedia.org/wiki/Automatic_dependent_surveillance_%E2%80%93_broadcast" class="markup--anchor markup--p-anchor">ADS-B</a>
transmissions of nearby aircraft, which includes information about its
location, altitude, speed, and more. Check out
<a href="https://www.rtl-sdr.com/adsb-aircraft-radar-with-rtl-sdr/" class="markup--anchor markup--p-anchor">this article about ADS-B</a>
for more info, or
<a href="https://www.rtl-sdr.com/tag/ads-b/" class="markup--anchor markup--p-anchor">these other cool projects</a>
that use ADS-B data.

#### Desktop SDR Software

-   <span
    id="8315"><a href="http://gqrx.dk/" class="markup--anchor markup--li-anchor">GQRX </a>— My
    personal favorite, runs on your favorite \*nix flavor (including mac
    OS!)</span>
-   <span
    id="6fe6"><a href="https://github.com/jopohl/urh" class="markup--anchor markup--li-anchor">URH (Universal Radio Hacker)</a> — Absolutely
    excellent software for reverse-engineering wireless protocols using
    SDR, which is useful for reverse-engineering.
    (Windows/Mac/OS X)</span>
-   <span
    id="a242"><a href="http://airspy.com/download/" class="markup--anchor markup--li-anchor">SDR# (pronounced “sdr-sharp”)</a> — Great
    for Windows users!</span>
-   <span
    id="b35d"><a href="http://kmkeen.com/rtl-demod-guide/" class="markup--anchor markup--li-anchor">rtl_fm</a> — Another
    favorite, really useful console SDR tools. Great for scripts, or for
    piping transmissions through sox/ffmpeg filter chains.</span>
-   <span
    id="0cfa"><a href="https://www.rtl-sdr.com/big-list-rtl-sdr-supported-software/" class="markup--anchor markup--li-anchor"><em>Click here for</em> <strong><em>✨Even More Software</em></strong></a><a href="https://www.rtl-sdr.com/big-list-rtl-sdr-supported-software/" class="markup--anchor markup--li-anchor"><strong><em>✨</em></strong></a><a href="https://www.rtl-sdr.com/big-list-rtl-sdr-supported-software/" class="markup--anchor markup--li-anchor"><strong><em>!</em></strong></a></span>

### Hardware

You can get the cheap stuff off of amazon/ebay/alibaba for around $6–10,
just search for “DVB-T” or “SDR”. Also, make sure you check out the
<a href="https://www.reddit.com/r/RTLSDR/wiki/compatibility" class="markup--anchor markup--p-anchor">list of compatible dongles</a>
(the only real requirement is that it’s based on the RTL2832U chipset).

If you have a lot of money to throw at things, here are some much
fancier, feature packed, and more expensive receivers. You probably
won’t need these.

-   <span
    id="0ea6"><a href="https://greatscottgadgets.com/hackrf/" class="markup--anchor markup--li-anchor">HackRF</a></span>
-   <span
    id="292a"><a href="https://www.nuand.com/" class="markup--anchor markup--li-anchor">BladeRF</a></span>
-   <span
    id="de7b"><a href="https://www.ettus.com/product/details/UB200-KIT" class="markup--anchor markup--li-anchor">USRP B200</a></span>
-   <span
    id="7bd2"><a href="http://www.limemicro.com/" class="markup--anchor markup--li-anchor">LimeSDR</a>
    (more cellular-oriented)</span>

### Cellular Stuff

-   <span
    id="9cc5"><a href="http://openbts.org/" class="markup--anchor markup--li-anchor">http://openbts.org/</a></span>

Interested in hacking cell phones? Cool! You can use OpenBTS to start
building your very own cellular network.

#### Sniffing GSM

-   <span
    id="f60e"><a href="https://z4ziggy.wordpress.com/2015/05/17/sniffing-gsm-traffic-with-hackrf/" class="markup--anchor markup--li-anchor">https://z4ziggy.wordpress.com/2015/05/17/sniffing-gsm-traffic-with-hackrf/</a></span>
-   <span
    id="17e2"><a href="https://www.rtl-sdr.com/rtl-sdr-tutorial-analyzing-gsm-with-airprobe-and-wireshark/" class="markup--anchor markup--li-anchor">https://www.rtl-sdr.com/rtl-sdr-tutorial-analyzing-gsm-with-airprobe-and-wireshark/</a></span>

The above are some great tutorials with plenty of information for
getting started sniffing GSM traffic. It even dumps the data into
Wireshark (nothing is
<a href="https://domonkos.tomcsanyi.net/?p=418" class="markup--anchor markup--p-anchor">decrypted</a>,
though, because that would be illegal!). *Note: if you want me to send a
copy of the VM I used in my presentation, you can find my contact
details*
<a href="https://www.ctis.me" class="markup--anchor markup--p-anchor"><em>here</em></a>*.
This would take a lot less time than compiling GNURadio.*

#### Detecting Stingrays

-   <span
    id="3397"><a href="https://www.schneier.com/blog/archives/2017/08/detecting_sting.html" class="markup--anchor markup--li-anchor">https://www.schneier.com/blog/archives/2017/08/detecting_sting.html</a></span>

A
<a href="https://en.wikipedia.org/wiki/Stingray_phone_tracker" class="markup--anchor markup--p-anchor">stingray</a>
is a device used to
<a href="https://en.wikipedia.org/wiki/Stingray_phone_tracker" class="markup--anchor markup--p-anchor">collect IMSI information</a>
of nearby cell phones. It does this by impersonating a BTS (cell tower),
and is often used for surveillance purposes (especially by police in
protest environments, for example). Use of stingrays by law enforcement
is a kind of passive surveillance that falls in a legal gray area, and
you can learn more about the legal implications of them
<a href="https://www.aclu.org/issues/privacy-technology/surveillance-technologies/stingray-tracking-devices" class="markup--anchor markup--p-anchor">here</a>.

There was a presenter as Shmoocon 2017 who built his own AMPS (1G)
network. Video of the presentation should be up in a few months.

That same guy was part of the NinjaTel group, who
<a href="https://arstechnica.com/information-technology/2012/07/ninja-tel-hacker-phone-network/" class="markup--anchor markup--p-anchor">brought their own cellular network to DEFCON 2012</a>
(Check out
<a href="https://en.wikipedia.org/wiki/NinjaTel_Van" class="markup--anchor markup--p-anchor">their van</a>!).

### Trunked Radio

-   <span
    id="f1b6"><a href="https://www.rtl-sdr.com/rtl-sdr-radio-scanner-tutorial-decoding-digital-voice-p25-with-dsd/" class="markup--anchor markup--li-anchor">https://www.rtl-sdr.com/rtl-sdr-radio-scanner-tutorial-decoding-digital-voice-p25-with-dsd/</a></span>
-   <span
    id="8155"><a href="https://www.rtl-sdr.com/rtl-sdr-tutorial-following-trunked-radio-unitrunker/" class="markup--anchor markup--li-anchor">https://www.rtl-sdr.com/rtl-sdr-tutorial-following-trunked-radio-unitrunker/</a></span>
-   <span
    id="ef19"><a href="http://notes.secretsauce.net/notes/2014/07/25_decoding-p25-with-rtl-sdr-on-debian.html" class="markup--anchor markup--li-anchor">http://notes.secretsauce.net/notes/2014/07/25_decoding-p25-with-rtl-sdr-on-debian.html</a></span>

Do you want to listen to your local police/fire
department/university/any organization using using radios on a
medium-large scale? Then welcome to the world of
<a href="https://en.wikipedia.org/wiki/Trunked_radio_system" class="markup--anchor markup--p-anchor">trunked (aka 2–way) radio</a>!

There are plenty of ways to listen in on trunked radio using SDR, though
you should note that many implementations will require that you use two
SDR dongles (one to listen to the control channel, the other to receive
transmission data). For those who want to listen in on the cheap, the
second link shows you how to set up
<a href="http://www.unitrunker.com/" class="markup--anchor markup--p-anchor">Unitrunker</a>
such that you can listen to trunked comms with just one dongle.

### **UCF Frequency Listings:**

What blog post would be complete without a big list of interesting,
localized things to tune to?

-   <span
    id="b81a"><a href="https://www.radioreference.com/apps/db/?sid=7165" class="markup--anchor markup--li-anchor">Talkgroup list</a>
    (for trunked comms- most walkies and so on will communicate this
    way)</span>
-   <span
    id="604b"><a href="https://www.radioreference.com/apps/db/?sid=3820" class="markup--anchor markup--li-anchor">Additional Talkgroups</a></span>
-   <span
    id="979a"><a href="https://www.radioreference.com/apps/db/?action=fle&amp;stid=12&amp;en=UNIVERSITY%20OF%20CENTRAL%20FLORIDA" class="markup--anchor markup--li-anchor">Listing of ALL FCC licenses registered to UCF</a></span>

Enjoy!

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [September 29, 2017](https://medium.com/p/6a256b04cdfd).

<a href="https://medium.com/@charltontrez/hucf-sdr-6a256b04cdfd" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

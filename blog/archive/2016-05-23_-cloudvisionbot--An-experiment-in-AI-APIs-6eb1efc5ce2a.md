@cloudvisionbot: An experiment in AI APIs
=========================================

I found myself in search of a quick project this weekend, eventually
settling on building yet another Twitter bot.

------------------------------------------------------------------------

### @cloudvisionbot: An experiment in AI APIs

<figure>
<img src="https://cdn-images-1.medium.com/max/600/1*KqpZAWUB4JHE6kr7Y0fqrQ.png" class="graf-image" alt="" />
</figure>

I found myself in search of a quick project this weekend, eventually
settling on building yet another Twitter bot.

Over the course of deciding what it was, exactly, that I wanted this bot
to do, I had an idea: Why not experiment with the recently introduced
<a href="https://cloud.google.com/vision/" class="markup--anchor markup--p-anchor">Google Cloud Vision API</a>
in order to tweet simple descriptions of the content of randomly
selected stock photos? After all, with the APIs already in place,
stitching everything together would certainly be easy enough.

And, as I had suspected, it really was that easy: so dead, scarily easy,
in fact, that I was able to get the thing working in a little over half
an hour starting from scratch. Not only was the Cloud Vision API simple
to configure, there were already
<a href="https://www.npmjs.com/search?q=google+vision" class="markup--anchor markup--p-anchor">numerous client libraries</a>
for it that were freely available on NPM. After registering for GCP and
the bot’s own Twitter, it was only a quick matter of getting things
working together in harmony.

And so,
<a href="https://twitter.com/cloudvisionbot" class="markup--anchor markup--p-anchor">@cloudvisionbot</a>
was brought into the world.

Much like its
<a href="http://twitter.com/nabgbot" class="markup--anchor markup--p-anchor">highly philosophical counterpart</a>,
CVbot runs on Node.js and is built upon Red Hat’s excellent
<a href="https://www.openshift.com/" class="markup--anchor markup--p-anchor">Openshift PaaS</a>
(which, incidentally, allows you to host up to 3 application instances
free of charge. Perfect for these sorts of small bots!).

Every hour, our curious little bot selects a beautiful image from
<a href="http://unsplash.com" class="markup--anchor markup--p-anchor">Unsplash</a>
at random, retrieves some descriptive matter from the Cloud Vision API,
and then tweets its findings. Very nice!

> [](https://twitter.com/cloudvisionbot/status/734509659177013250)

An obvious description, yes, though eerily human

As always, all of the code behind this project is
<a href="https://github.com/ctrezevant/cloud-vision-bot" class="markup--anchor markup--p-anchor">available on my GitHub</a>,
and is likely to improve over the next few days as I get everything
fine-tuned.

Enjoy!

By
<a href="https://medium.com/@charltontrez" class="p-author h-card">Charlton Trezevant</a>
on [May 23, 2016](https://medium.com/p/6eb1efc5ce2a).

<a href="https://medium.com/@charltontrez/cloudvisionbot-an-experiment-in-ai-apis-6eb1efc5ce2a" class="p-canonical">Canonical link</a>

Exported from [Medium](https://medium.com) on September 20, 2019.

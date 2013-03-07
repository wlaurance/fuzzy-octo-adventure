{"title":"Nodejitsu","date":"3-7-2013"}

Recently I have switched from running node.js apps on heroku to
nodejitsu. The development experience is so so much better. Nodejitsu
focuses solely on node.js while heroku provides support for many
languages/platforms but is know for great Rails support.

Nodejitsu doesn't have a free tier; however, they do offer a sandbox for
a month or two (if you input a credit card). But their least expensive
plan starts around $3 a month. I have no issue paying money for this
great development experience. 

Heroku uses a few different abstractions that relate to app performance
such as web and worker dynos. Nodejitsu allows multiple drones to exist
which are essentially copies of your app that are behind a load
balancer.

How effective are Nodejitsu's drones? Lets find out

<script src="https://gist.github.com/wlaurance/5109356.js"></script>

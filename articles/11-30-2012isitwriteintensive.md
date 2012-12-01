{"title":"Is that write intensive","date":"11-30-2012"}

Today I had a discussion with [@rfc2616](https://twitter.com/rfc2616),
Rob Heittman, about mongoDB. We discussed replica sets, write concerns
and other [web scale concerns](http://www.youtube.com/watch?v=b2F-DItXtZs). I am trying to figure out if an app I am working on
is write intensive.

Rob put it this way; Unless you have a HD telescope streaming a live
feed to your app, its probably not write intensive. Typically for
smaller business apps, mine is a time tracking app, any human requested
data will be hard to match a high bandwidth data stream hitting your
app.

We love mongoDB and nosql because we realize its place and that it is
not a replacement for RDMS. However we still enjoy nosql memes and the
frustrated haters.

<iframe class="youtube-player" type="text/html" width="640" height="385" src="http://www.youtube.com/embed/hEqQMLSXQlY" frameborder="0"></iframe>

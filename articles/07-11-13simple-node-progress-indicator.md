{
  "title" : "Node.js Simple Progress Indicator Using Charm", 
  "date" : "7/11/2013",
  "author" : "wlaurance"
}

Charm is a module used to write colors and cursor positions to a stream.

![substacks's lucky charms](http://substack.net/images/charms.png)

Let's build a simple progress indicator with charm.

```
  npm install charm
```

###Simple charm bar

<script src="https://gist.github.com/wlaurance/5980479.js"></script>

Using setTimeout to write a charm bar. Because charm bar writes using
the stream interface, using a blocking while loop will not write.

###HTTP charm bar

<script src="https://gist.github.com/wlaurance/5980708.js"></script>

Download the latest release of node and tick the charm bar on each
chunk. Because `req.on('data'...` makes many trips around the event
loop, charm.write will actually write to the stream its piped to. In
this case process.stdout.

###HTTP Disco Charm Bar

<script src="https://gist.github.com/wlaurance/5980789.js"></script>

Same as the HTTP charm bar, but set the foreground color disco style!!


There you go, a simple way to write progress indicators in node.


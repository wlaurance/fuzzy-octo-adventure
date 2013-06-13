{
  "title" : "Ember.js", 
  "date" : "06/07/2013",
  "author" : "wlaurance"
}

I have recently dove into the world of Ember.js. Great you say? I say one day.
The main reason I say this is Ember Data. It frustrates me.

##REST Routes

I want to nest models but the REST routes do not actually nest.
Generally speaking Data wants all resources to be at the root of your API.
Perhaps this is a great way to design REST APIs. However, it would be very difficult to adapt an Ember App to an API already in production. Sure, you can hack the urls, or just use $.getJSON, but there needs to be a way where to specify
 a REST API paradigm. But if the API is hod podge chances are you are not
using an MVC like Ember or not using Ember Data at all.

I guess what pisses me off is Ember is telling me how to write my REST API. Which means I am implementing a RESTful API according to the Ember Data Dev Teams
idea of RESTfulness. Not sure how I feel about this. Not that I do not trust Tom Dale or other.

The routes could look like:
```
/posts
/comments
/tags
/posts/1
/comments/5
```

or 

```
/posts
/posts/1/comments
/posts/1/tags
```

I like the second. 

The first way is more railsy imo.

Ideally I want to pass ember-data a flag that says "nestedAPIStyle":true

So it will build the routes like number 2.

##Doesn't seem to work with Jam

I want to use ember with AMD, require style, or Jam but it does not work ATM.
Since Ember Data requires Ember, it makes it hard to use AMD style to load Ember Data.

Something like this will most likely fail.

```
require(["jquery", "ember", "ember-data"], function($, Ember, DS){
 
})
```

Because Ember is not in the namespace, ember-data fails. Perhaps these three particular libraries should always be in the global namespace? (my javascript kick
is to clear the global ns) I want to write my Ember Apps in a more modular style and when I tried to use them in AMD fashion it broke and made me sad.




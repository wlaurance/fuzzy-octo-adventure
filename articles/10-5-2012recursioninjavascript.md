{"title":"Recursion in JavaScript","date":"10-5-2012","author":"wlaurance"}

Here is a snippet of code where I use recursion in a Titanium project.
Basically it is a JSON.stringify like function that's terminating
condition is the typeof(hash) isnt 'object' ie a primative and ready for
me stuff it in a label object.

```
  labels = [];
  getObjectProps = function(hash) {
    var key, value, _results;
    _results = [];
    for (key in hash) {
      value = hash[key];
      if (typeof value === 'object') {
        _results.push(getObjectProps(value));
      } else {
        if (key !== 'type' && key !== 'name' && key !== 'optional') {
          _results.push(labels.push(Ti.UI.createLabel({
            text: format.cleanBodyText(String(value)),
            height: Ti.UI.SIZE,
            color: colors.white,
            width: Ti.UI.FILL,
            touchEnabled: false,
            font: {
              fontSize: key === 'textRaw' ? '16dp' : '14dp',
              fontWeight: key === 'textRaw' ? 'bold' : 'regular'
            }
          })));
        } else {
          _results.push(void 0);
        }
      }
    }
    return _results;
  };
  getObjectProps(_this.currentLevel[e.source.key]);

```

Here is the same in coffee

```
labels = []
getObjectProps = (hash)->
  for key,value of hash
    if typeof(value) is 'object'
      getObjectProps value
    else
      if key not in ['type', 'name', 'optional']
        labels.push Ti.UI.createLabel
          text: format.cleanBodyText String value
          height:Ti.UI.SIZE
          color:colors.white
          width:Ti.UI.FILL
          touchEnabled:false
          font:
            fontSize:if key is 'textRaw' then '16dp' else '14dp'
            fontWeight:if key is 'textRaw' then 'bold' else 'regular'
getObjectProps @currentLevel[e.source.key]

```

As long as you do not involve any asyncish code everything will be good. 

Adding callbacks to recursive is a tricky business because recursion
works on the underlying principle of functions waiting for others to
return. So this leads me to question why recursion and callback (async)
styles would ever mix?

###Let the panic commence

Initial thoughts. Callbacks and recursion would make
[memoization](http://en.wikipedia.org/wiki/Memoization) interesting. In
a way, we can "pretend" that returning is nonexistent and pass in a
callback function where we would return the finished result. 

For saving space, I will show examples in coffee only.

WIP

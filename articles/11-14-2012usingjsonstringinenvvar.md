{"title":"Using JSON string in env var","date":"11-14-2012"}

You can. Why not? It's just a string.

```
JSON=`node -e "console.log(JSON.stringify({a:'hi im json',
b:['what','up','yo']}));"`
echo $JSON
```

For solving Glog config, which is a .json file, I can set a env variable
on Heroku to be this config string.

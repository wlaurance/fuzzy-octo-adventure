{"title":"Nginx redirect for multiple virtual hosts","date":"8-16-2012","author":"wlaurance"}

If you want to redirect traffic to a different subdomain, you can add a
rewrite clause into each of your server{} entries in
/etc/nginx/sites-avaliable/default or where ever you keep your available
sites located. 

This setup still allows me to have multiple virtual hosts on the same
box behind an nginx reverse proxy.

For this example, I have a DNS A record for examplehost1.com,
blog.examplehost1.com and www.examplehost1.com pointing to the same IPv4
address. examplehost2.com and www.examplehost2.com have their own A
records pointing to a the same IPv4 address.

Nginx will match the incomming server name in the headers of the
request. If the server name is examplehost1.com, nginx will send a 301
redirect in the response to 'http://www.examplehost1.com'. The same
applies if the server name in the request is blog.example1.com. When the
server name is 'www.examplehost1.com', nginx passes the request to the
specified proxy. The reason I have this is there are links out in the
world with the blog subdomain, but now I want all traffic to end up at
www.examplehost1.com.

The examplehost2.com will make sure all of its traffic ends up at
www.examplehost2.com.

There are other methods of redirection, but I find this the easiest when
you have multiple virtual hosts setup on an nginx reverse proxy.


/etc/nginx/sites-available/default
```
server{
  server_name examplehost1.com;
  rewrite ^/(.*) http://www.examplehost1.com permanent;
}
server{
  server_name blog.examplehost1.com;
  rewrite ^/(.*) http://www.examplehost1.com permanent;
}
server{
  server_name www.examplehost1.com;
  location / {
    proxy_pass http://127.0.0.1:3000;
  }
}
server{
  server_name www.examplehost2.com;
  location / {
    proxy_pass http://127.0.0.1:3001;
  }
}
server{
  server_name examplehost2.com;
  rewrite ^/(.*) http://www.examplehost2.com permanent; 
}
```

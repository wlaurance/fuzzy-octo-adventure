{"title":"Node on Heroku Caveats","date":"11-12-2012"}

[Heroku](https://www.heroku.com/) is an awesome web app platform.
Hands down it has one of the best deployment strategies.
```
git push heroku master
```
Its that simple. In the past couple of years, Heroku has added support
for node. They have done an excellent job by using npm and providing
numerous tutorials. I have been deploying node apps on Heroku for a
few months and I want to share with you a few caveats I have found.

1. **Set Timeouts/Interval**. The key thing to remember about Heroku is that
   your app will go to sleep without any activity. I have an app in the
   works that uses a mongodb instance on ec2 as a session store. The npm module
   I am using will run a "clear" function on a set interval. If it so
   happens that the slug is asleep, this clear function is never fired.
   From what I can tell, it actually will never fire again.

The *typical* solution you will hear for #1 is Pingdom. Although it will
work, it is pricey. Another factor to consider is why you chose Heroku
in the first place. Inexpensive scalable web hosting. The reason why
slugs sleep after a certain period of inactivity is so Heroku can keep
their costs down, in turn keeping your costs down. 

I am leaning towards [Iron
Worker](https://addons.heroku.com/iron_worker). You can get Five free
hours as the starter plan.

Using [Glog](https://github.com/guyht/glog) on heroku no longer seems to
be a problem. At the time this post was written, Glog will not work out
of the box on heroku, but with a few adjustments it works great.
   

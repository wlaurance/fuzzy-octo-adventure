{"title":"Billable","date":"6-1-2012"}

As a freelance software developer I often find myself asking whether
what I am doing at the moment is worth my time. Am I getting paid to do
this specific task? Is my solution *good enough*? I use
[Freshbooks](http://www.freshbooks.com) for invoicing clients and
tracking my time on projects. Although it feels like I have worked close
to 40 hours, my *Billable* time is not quite hitting the mark. Perhaps
this is due to missing certain tasks in my time logs. Starting a new
task without punching the clock. For whatever reason my time log
sometimes does not reflect my time spent working. Even when my time logs
do reflect the time spent, I haven't the slightest idea what I spent the
time on. Freshbook's timer doesn't require me to leave a message and
when I do its usually vauge.

Its time to venture into new territory. Ideally I want to track my time
with git. I have read a
[few](http://andy.delcambre.com/2008/02/06/git-time-tracking.html)
[blog](http://mir.aculo.us/2009/10/12/instant-time-tracking-from-git-commit-messages/)
[articles](https://github.com/rcrowley/gitpaid) and I have checked out
some [products](http://letsfreckle.com/). I am going to use a new git
CLI based time tracking system.

Freshbooks has a decent api, so I should be able to integrate well with
this. I also use [assembla](https://www.assembla.com/) for many client
projects and github for others. Both assembla and github provide means
to call webhooks. Ideally I want to "build" a system using existing
components rather than building a new system from scratch.


### Example project

++Ditaa++

--Ditaa--

In restaurant app, all client branches share one common repo that
contains the base restaurant functionalities. Each client repo has its
own local copy of the restaurant repo but any changes must be compatible
with all clients. To acheive this, I use configuration objects in the
client repositories which restaurant repo reads and decides what to do.
There is even the possibility of just handing app control over to the
client repo by overriding a class or what not.

My time is mainly spent in the client repos and not a standalone version
of restaurant app. Thus the tool would need to be able to handle
multiple repositories for the same project and have a pause button of
sorts unless I assume time between commits is 100% put towards the diff
of said commit.



TBC

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

Hustle and Flow
---------------

WIP, Comments welcome for ideal workflow git time tracking
because I am not quite sure the way I want to do this. I guess the time
tracking strategy would vary between workflow types. 

I hope to add support for [ditaa](http://ditaa.org/ditaa/) soon to my
glog and I will be able to show you a cool ascii text graph for my
workflow.

### Example project

In Restaurant App I have one repository that houses code for all of my
client projects. Each client has their own branch and all of the shared
code is in master. Client branches typically house specific assets to
their branding.

When working on a small feature needed for one client, I will typically
stay in the client branch and make the necessary changes, keeping any
client specific changes in different commits than any shared code.

I then checkout master and cherry-pick those shared code commits, then
merge my master to other client branches, so everyone is up to date. On
the reverse, when coding up major features and fixes, I am checked out
on master, and will merge the patches to my client branches.

So theres is a lot of branch switching, picking, merging and squashing
going on. It would be nice if I could just have a system so intelligent
that it knows exactly how much time I have worked on a certain project.

Since that is not feasible, I would like to have a sprint type method. I
start by pressing a start timer. The first commit after the timer will
have the difference of commit time and timer as its running time. Each
subsequent commit will just have the difference of the previous commit
as its time.

This type of system assumes that I am indeed working a project between
each commit continously. This is generally the case, but there would
need to be a *pause* button so I could eat lunch or something.

By tying commit messages to my tracked time, I believe I can get a much
better picture of what I am spending my time on.

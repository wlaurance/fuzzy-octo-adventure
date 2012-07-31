{"title":"Titanium Java Version","date":"7-31-2012","author":"wlaurance"}

According to
[Appcelerator](http://docs.appcelerator.com/titanium/2.1/#!/guide/Installing_Oracle_JDK)
only Oracles JDK will suffice. I have successfully build dev and
production apk's with open-jdk-7 on Ubuntu 12.04.

The Oracle JDK is used to compile javascript into 'Java' using jar files
found in the titanium sdk. Most of the other tasks use Android SDK tools
so the java jdk you have is not too important. 

I was unable to make it work with openjdk 6 but it works well with 7.
Here is my java -version 

```
java version "1.7.0_03"
OpenJDK Runtime Environment (IcedTea7 2.1.1pre)
(7~u3-2.1.1~pre1-1ubuntu3)
OpenJDK Server VM (build 22.0-b10, mixed mode)
```

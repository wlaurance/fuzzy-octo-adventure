{"title":"Titanium Java Version","date":"7-31-2012","author":"wlaurance"}

According to
[Appcelerator](http://docs.appcelerator.com/titanium/2.1/#!/guide/Installing_Oracle_JDK)
only Oracles JDK will suffice. I successfully build dev and
production apk's daily with open-jdk-7 on Ubuntu 12.04.

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

javac -version

```
javac 1.6.0_24
```

and uname -a

```
Linux icky 3.2.0-27-generic-pae #43-Ubuntu SMP Fri Jul 6 15:06:05 UTC 2012 i686 i686 i386 GNU/Linux
```
The only issue with using open-jdk 7, is the final zip check will hang.
But you can safely ctrl c after a few seconds.

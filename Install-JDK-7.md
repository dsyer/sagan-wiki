### Goal

Sagan depends on a minimum of JDK 7 to build and run. If you already have this installed, skip below to [verify the Gradle build runs against it](#verify).

### Prerequisites

 - _None_

### Steps

#### Install

 - [Download and install a JDK for your platform from java.net](https://jdk7.java.net/download.html).

 - Once installed, verify that JDK binaries are properly on your PATH:

    $ javac -version
    javac 1.7.0_08-ea

<a name="verify"/>    
#### Verify Gradle uses correct JDK installation

> _**Tip:** New to Gradle? Check out our [[Gradle tips]]._

 - Run the following command from the root of your sagan repository:
```
$ ./gradlew -version

------------------------------------------------------------
Gradle 1.11
------------------------------------------------------------

Build time:   2014-02-11 11:34:39 UTC
Build number: none
Revision:     a831fa866d46cbee94e61a09af15f9dd95987421

Groovy:       1.8.6
Ant:          Apache Ant(TM) version 1.9.2 compiled on July 8 2013
Ivy:          2.2.0
JVM:          1.7.0_08-ea (Oracle Corporation 23.2-b09)
OS:           Mac OS X 10.9.2 x86_64
```

Take note of the `JVM` entry above, and make sure it reads `1.7.0` (or greater). If it does not, check the value of your `JAVA_HOME` environment variable.

### Next Steps

Return to [[set up environment]].
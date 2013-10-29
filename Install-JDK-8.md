
## 1. Install JDK 8

The Sagan application is implemented using the latest Java SE 8 language features, and this means that you'll need to [install OpenJDK 8](https://jdk8.java.net/download.html), build 108 or greater.

Once installed, verify that JDK 8 binaries are properly on your PATH:

    $ java -version
    java version "1.8.0-ea"
    Java(TM) SE Runtime Environment (build 1.8.0-ea-b108)
    Java HotSpot(TM) 64-Bit Server VM (build 25.0-b50, mixed mode)

### Double-check JDK 8 installation

    $ ./gradlew -version

    ------------------------------------------------------------
    Gradle 1.8
    ------------------------------------------------------------

    Build time:   2013-09-24 07:32:33 UTC
    Build number: none
    Revision:     7970ec3503b4f5767ee1c1c69f8b4186c4763e3d

    Groovy:       1.8.6
    Ant:          Apache Ant(TM) version 1.9.2 compiled on July 8 2013
    Ivy:          2.2.0
    JVM:          1.8.0-ea (Oracle Corporation 25.0-b50)
    OS:           Mac OS X 10.8.3 x86_64

Take note of the `JVM` entry above, and make sure it reads `1.8.0`. If it doesn't, then revisit the instructions in [[Install JDK 8]].


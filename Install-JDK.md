### 1. Install JDK

The Sagan application requires JDK 7 or better. You can [download and install a JDK for your platform from java.net](https://jdk7.java.net/download.html).

> _Note: Sagan runs perfectly well on the newly-released JDK 8 as well._

Once installed, verify that JDK 7 binaries are properly on your PATH:

    $ java -version
    java version "1.7.0_60-ea"
    Java(TM) SE Runtime Environment (build 1.7.0_60-ea-b04)
    Java HotSpot(TM) 64-Bit Server VM (build 24.60-b07, mixed mode)
    
#### Double-check JDK 7 installation

    $ ./gradlew -version

    ------------------------------------------------------------
    Gradle 1.10
    ------------------------------------------------------------

    Build time:   2013-12-17 09:28:15 UTC
    Build number: none
    Revision:     36ced393628875ff15575fa03d16c1349ffe8bb6

    Groovy:       1.8.6
    Ant:          Apache Ant(TM) version 1.9.2 compiled on July 8 2013
    Ivy:          2.2.0
    JVM:          1.7.0_60-ea (Oracle Corporation 24.60-b07)
    OS:           Mac OS X 10.9.1 x86_64

Take note of the `JVM` entry above, and make sure it reads `1.7.0`. If it doesn't, then revisit the instructions in [[Install JDK]].

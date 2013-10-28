
## 1. Install JDK 8

The Sagan application is implemented using the latest Java SE 8 language features, and this means that you'll need to [install OpenJDK 8](https://jdk8.java.net/download.html), build 108 or greater.

Once installed, verify that JDK 8 binaries are properly on your PATH:

    $ java -version
    java version "1.8.0-ea"
    Java(TM) SE Runtime Environment (build 1.8.0-ea-b108)
    Java HotSpot(TM) 64-Bit Server VM (build 25.0-b50, mixed mode)

... and *that's it!* No app servers to install, no build systems to download. Plain old Java is all you need.

## 2. Grab the code

The recommended approach is to [fork and clone][fork] this repository using Git – this will allow you maximum freedom to make changes, commit and push them to your own repository, share with others, and issue pull requests.

You can also check out the repository using Subversion if that's more convenient, or you can simply download a zip file of the repository. All of these options are available from the clone / download widget to your right.

## 3. Build and run

The Sagan app is built using [Spring Boot][boot], which makes running any application as simple as executing a jar file.

First, assemble the JAR file using the built-in Gradle wrapper script:

    $ ./gradlew :sagan-site:build -x integTest

> **NOTE**: the `-x integTest` argument above skips longer-running integration tests in the interest of time.

Then run the app with `java -jar`:

    $ java -jar sagan-site/build/libs/sagan-site.jar

A few seconds later you'll see a log entry to the effect of

    sagan.app.site.ApplicationConfiguration  : Started ApplicationConfiguration in 8.455 seconds

And that means you can now browse the site at <http://localhost:8080>. Enjoy!

## Alternative, even faster ways to build and run

While it's important to understand the simple process of building and executing a jar as detailed above, an even more convenient approach is to use the `run` Gradle task:

    $ ./gradlew :sagan-site:run

And since the application is ultimately bootstrapped via a standard Java `main` method, you can also run the app directly from within your IDE. See [[Import sources into IDE]] for details.

[fork]: https://help.github.com/articles/fork-a-repo
[boot]: http://spring.io/spring-boot

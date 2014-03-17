### Goal

Run the Sagan site application locally, so that it can be browsed at <http://localhost:8080>.

### Prerequisites

1. [[Get the source]]
1. [[Install JDK 7]]

### Steps

#### Option 1: Build and run from an executable JAR

The Sagan app is built using [Spring Boot][boot], which makes running any application as simple as executing a jar file.

First, assemble the JAR file for the site:

    $ ./gradlew :sagan-site:build -x check

> _**NOTE**: the `-x check` argument above skips running tests in the interest of time._

Then run the app with `java -jar`:

    $ java -jar sagan-site/build/libs/sagan-site.jar

A few seconds later you'll see a log entry to the effect of

    sagan.SiteMain  : Started SiteMain in 8.455 seconds

And that means you can now browse the site at <http://localhost:8080>. Enjoy!

#### Option 2: Run directly from the build system

While it's important to understand the simple process of building and executing a jar as detailed above, an even more convenient approach is to use the `run` Gradle task:

    $ ./gradlew :sagan-site:run

#### Option 3: Run directly from within the IDE

Assuming that you have followed the instructions to [[use an IDE]], you can easily run the application by opening the `sagan.SiteMain` class and executing it's `main()` method.


### Next steps

 - [[Enable search locally]]
 - [[Import production data]]
 - [[Enable admin access locally]]

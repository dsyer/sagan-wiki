Gradle is a fantastic build tool--a complete _project automation tool_, really; but lots of folks still haven't had the chance to use it. Here are a few tips that we've found useful along the way.

Sagan uses the [Gradle](http://gradle.org) build system, and thanks to the [Gradle wrapper](http://www.gradle.org/docs/current/userguide/gradle_wrapper.html), there's nothing you need to install. Running the `./gradlew` script as above (or `gradlew.bat` on Windows) will fetch and use the correct Gradle binaries if you don't already have them installed on your system._

Consider installing the [`find-gradle`](https://github.com/cbeams/shell-scripts/blob/master/find-gradle) convenience script if you'd like to avoid the need for relative pathing (e.g. typing `./` or `../`) in order to invoke `gradlew`. *nix systems only.

[Getting Started Building Java Projects with Gradle](https://spring.io/guides/gs/gradle/) is a Getting Started Guide on spring.io designed to make Gradle's basic concepts clear.

Gradle's user guide is a wonderful, well-written resource for understanding Gradle from the ground up.

Also check out the [gradle.org/books](http://gradle.org/books).
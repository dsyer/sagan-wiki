### Goal

Compile, run tests, and assemble the executable JAR files for the Sagan *indexer* and *site* applications.

### Prerequisites

1. [[Get the source]]
2. [[Install JDK 7]]

### Steps

#### Build

The following command will build both the Sagan site and indexer applications, running all unit and integration tests along the way:

    ./gradlew build

> _**NOTE**: Sagan uses the [Gradle](http://gradle.org) build system, and thanks to the [Gradle wrapper](http://www.gradle.org/docs/current/userguide/gradle_wrapper.html), there's nothing you need to install. Running the `./gradlew` script as above (or `gradlew.bat` on Windows) will fetch and use the correct Gradle binaries if you don't already have them installed on your system._
    
> _**TIP**: Check out the [`find-gradle`](https://github.com/cbeams/shell-scripts/blob/master/find-gradle) convenience script if you'd like to avoid relative pathing to the `gradlew` script._
    
> _**TIP**: if you wish to skip longer-running integration tests, run the above with `-x integTest`. See also Gradle's documentation on [excluding tasks](http://www.gradle.org/docs/current/userguide/tutorial_gradle_command_line.html#sec:excluding_tasks_from_the_command_line)._


#### Verify

When the build is complete, you should now have the following two JARs in place:

    sagan-site/build/libs/sagan-site.jar
    sagan-indexer/build/libs/sagan-indexer.jar

### Next steps

You're now ready to [[import into IDEA or Eclipse]] or you can [[run the site locally]] straight away.



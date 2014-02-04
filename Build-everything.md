### Goal

Compile, run tests, and assemble the executable JAR files for the Sagan applications.

### Prerequisites

1. [[Get the code]]
2. [[Install JDK]]

### Steps

#### Build

The following command will build both the Sagan site and indexer applications, running all unit and integration tests along the way:

    ./gradlew build

> **TIP**: if you wish to skip longer-running integration tests, run the above with `-x integTest`. See also Gradle's documentation on [excluding tasks][].

#### Verify

When the build is complete, you should now have the following two JARs in place:

    sagan-site/build/libs/sagan-site.jar
    sagan-indexer/build/libs/sagan-indexer.jar

### Next steps

You're now ready to [[Run the site locally]].


[excluding tasks]: http://www.gradle.org/docs/current/userguide/tutorial_gradle_command_line.html#sec:excluding_tasks_from_the_command_line

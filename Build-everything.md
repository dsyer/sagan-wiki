### Goal

Compile, run tests, and assemble the executable JAR files for the Sagan *indexer* and *site* applications.

### Prerequisites

1. [[Get the source]]
1. [[Install Node.js]]
1. [[Install JDK 7]]

### Steps

#### Build

From within the root directory of your repository, the following command will build both the Sagan site and indexer applications, running all unit and integration tests along the way:

> _**Tip:** New to Gradle? Check out [[Gradle tips]]!_

    ./gradlew build

Or, on Windows:

    gradlew.bat build


When the build is finished, you should see the following:
```
BUILD SUCCESSFUL
```

### Next steps

You're now ready to [[import into IDEA or Eclipse]] or you can [[run the site locally]] straight away.


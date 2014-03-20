### Goal

Import sagan sources into your IDE of choice.
### Prerequisites

1\. Install the latest version of [STS](http://spring.io/tools/sts), [Eclipse](http://eclipse.org/downloads) or [Intellij IDEA](http://www.jetbrains.com/idea).
> _**Note**: The instructions here have been tested against STS 3.4.0, IDEA 13.0.2 and 13.1._

2\. [[Build everything]]
> _**Note**: It is important to first build everything from the command line to ensure that everything works as expected before importing into your IDE._


### Steps

> _**NOTE**: Both IDEA and Eclipse (STS, anyway), have dedicated support for directly importing Gradle-based projects. At the time of this writing, however, the sagan development team recommends using the `gradle idea` and `gradle eclipse` commands as below to generate IDE project metadata. Feel free to try importing directly from the build.gradle files if you wish, but what follows is the officially supported approach for now._

#### IDEA

1. Run `./gradlew idea` from the root directory of your sagan repository clone.
1. Open IDEA.
1. If any projects are open, click File->Close Project for each.
1. From the "Welcome to IntelliJ IDEA" screen, click "Open Project".
1. Navigate to the root directory of your sagan repository clone.
1. Click "Choose".
1. You should now have all sources imported without errors.

#### Eclipse/STS

1. Run `./gradlew eclipse` from the root directory of your sagan repository clone.
1. In Eclipse / STS, click File->Import->Existing Projects into Workspace.
1. In the "Select root directory" field, click "Browse" and navigate to the root directory of your sagan repository clone and click "Open".
1. Check the "Search for nested projects" box.
1. You should now see five projects selected as follows:
 - [x] sagan
 - [x] sagan-client
 - [x] sagan-common
 - [x] sagan-indexer
 - [x] sagan-site
1. Click "Finish".
1. You should now have all sources imported without errors.

### Next steps

You may now want to [[run the site locally]], and if you haven't already, this is a good time to read [[how things fit together]].
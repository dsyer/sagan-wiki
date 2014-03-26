### Goal

Import Sagan project sources into your IDE of choice.
### Prerequisites

 - [[Set up environment]]
 - Install the latest version of [STS](http://spring.io/tools/sts), [Eclipse](http://eclipse.org/downloads) or [Intellij IDEA](http://www.jetbrains.com/idea)

> _**Note:** The steps below have been tested against STS 3.4.0, IDEA 13.0.2 and 13.1._


### Steps

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
1. Click "Finish".
1. You should now have all sources imported without errors.

### Next steps

At this point, you may want to [[build everything]] or [[run the site locally]] if you have not already.

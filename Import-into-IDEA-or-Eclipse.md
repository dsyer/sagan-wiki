### Goal

Import Sagan project sources into your IDE of choice.
### Prerequisites

 - [[Set up environment]]
 - Install the latest version (4.2.0 or better) of the [Spring Tool Suite](http://spring.io/tools/sts) or [Intellij IDEA](http://www.jetbrains.com/idea)

> _**Note:** The steps below have been tested against STS 4.2.1 and IDEA 14._


### Steps

#### IDEA

1. Open IDEA.
1. If any projects are open, click File->Close Project for each.
1. From the "Welcome to IntelliJ IDEA" screen, click "Open Project".
1. Navigate to the root directory of your sagan repository clone.
1. Click "Choose".
1. Click File->Project Structure->Project and select "8.0" as project language level
1. You should now have all sources imported without errors.

#### Spring Tool Suite

1. In STS, click File->Import->Gradle->Existing Gradle Project
1. In the "Select root directory" field, click "Browse" and navigate to the root directory of your Sagan repository clone and click "Open".
1. Click "Finish".
1. You should now have all sources imported without errors.

### Next steps

At this point, you may want to [[build everything]] or [[run the site locally]] if you have not already.

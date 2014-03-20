### Goal

Run the Sagan site application locally, so that it can be browsed at <http://localhost:8080>.

### Prerequisites

1. [[Get the source]]
1. [[Install Node.js]]
1. [[Install JDK 7]]

### Steps

1\. From the root directory of your sagan repository, run the following:
```
./gradlew :sagan-site:bootRun
```

2\. After a few seconds, you should see:
```
sagan.SiteMain  : Started SiteMain in 8.455 seconds
```

3\. Go to <http://localhost:8080>.

#### Option 3: Run directly from within the IDE

Assuming that you have followed the instructions to [[use an IDE]], you can easily run the application by opening the `sagan.SiteMain` class and executing it's `main()` method.


### Next steps

 - [[Enable search locally]]
 - [[Import production data]]
 - [[Enable admin access locally]]

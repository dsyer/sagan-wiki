### Goal

Run the Sagan site application locally, so that it can be browsed at <http://localhost:8080>.

### Prerequisites

1. [[Set up environment]]

### Steps

1\. From the root directory of your sagan repository, run the following:
```
./gradlew :sagan-site:bootRun
```

> _**Note:** Spring Boot also allows running apps with the `java -jar` command, but this feature is not yet available in Sagan - see [#191](https://github.com/spring-io/sagan/pull/191) for more details._

2\. After a few seconds, you should see:
```
sagan.SiteMain  : Started SiteMain in 8.455 seconds
```

3\. Go to <http://localhost:8080>.


### Next steps

At this point, you may want to [[build everything]] or [[import into IDEA or Eclipse]] if you have not already.

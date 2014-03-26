### Goal

Run the Sagan site application locally, so that it can be browsed at <http://localhost:8080>.

### Prerequisites

 - [[Set up environment]]

### Steps

From the root directory of your sagan repository, run the following:
```
./gradlew :sagan-site:bootRun
```

> _**Note:** Spring Boot also allows running apps with the `java -jar` command, but this feature is not yet available in Sagan - see [#191](https://github.com/spring-io/sagan/pull/191) for more details._

After a few seconds, you should see:
```
sagan.SiteMain  : Started SiteMain in 8.455 seconds
```

Now, go to <http://localhost:8080> and you should see homepage. Click around and explore a bit—you should find the site is identical in every way to what you see at [spring.io](http://spring.io).

> _**Note:** The one exception to the above is search. Out of the gate, you'll get 500 errors when you try to perform a search. To remedy this, you'll need to [[enable search locally]]._


### Next steps

At this point, you may want to [[build everything]] or [[import into IDEA or Eclipse]] if you have not already.

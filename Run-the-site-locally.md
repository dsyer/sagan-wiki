### Goal

Run the Sagan site application locally, so that it can be browsed at <http://localhost:8080>.

### Prerequisites

 - [[Set up environment]]

### Steps

#### Run the site locally from your IDE

Create a new run configuration with the class `sagan.SiteApplication`. Make sure that this configuration refers to the `sagan-site` folder as a working directory. Some IDEs, like IntelliJ, support predefined variables like `$MODULE_DIR$`.

Then use this run configuration to start the site!

> _**Note:** Sagan is using [Spring Boot's developer tools features](http://docs.spring.io/spring-boot/docs/current/reference/html/using-boot-devtools.html), such as LiveReload.


#### Run the site locally from the command line
From the root directory of your sagan repository, run the following:

> _**Tip:** New to Gradle? Check out [[Gradle tips]]!_

```
./gradlew :sagan-site:bootRun
```

After a few seconds, you should see:
```
sagan.SiteApplication : Started SiteApplication
```

Now, go to <http://localhost:8080> and you should see homepage. Click around and explore a bit—you should find the site is identical in every way to what you see at [spring.io](http://spring.io).

> _**Note:** The one exception to the above is search. Out of the gate, you'll get 500 errors when you try to perform a search. To remedy this, you'll need to [[enable search locally]]._


### Next steps

At this point, you may want to [[build everything]] or [[import into IDEA or Eclipse]] if you have not already.
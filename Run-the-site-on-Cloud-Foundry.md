### Goal

Get the Sagan web app up and running under your own Cloud Foundry account.

### Prerequisites

1. [[Get started with Cloud Foundry]]
1. [[Get the source]]

### Steps

#### Build the executable sagan-site JAR

    $ cd $SAGAN_HOME/sagan-site
    $ ../gradlew build -x check

> _**Note:** When the above is complete, you will find the JAR file at `build/libs/sagan-site.jar`_

#### Push the site to Cloud Foundry

In the command below, you will provide a `-n` argument, which will be used to form the URL `http://[host].cfapps.io`. The recommended host naming scheme is `$GHUSER-sagan`, where `$GHUSER` is your personal GitHub username. This approach helps avoid naming conflicts with other users who are deploying the Sagan app to Cloud Foundry under the shared `cfapps.io` domain. The host value of `cbeams-sagan` is used as an example below.

    $ cf push sagan -n cbeams-sagan

You should now see output similar to the following, as the app is uploaded and started:

    Creating app sagan in org bclozel / space development as brian@clozel.fr...
    OK
    Creating route bclozel-sagan.cfapps.io...
    OK
    Binding bclozel-sagan.cfapps.io to sagan...
    OK
    Uploading sagan...
    Uploading from: /Users/bclozel/workspace/sagan/sagan-site
    82.6M, 256 files    

    

#### Explore the running site

You should now be able to visit the site at http://[host].cfapps.io and browse around. You will notice that search functionality does not yet work and that the blog and team pages are empty.


### Next steps

At this point, the app is running against an in-memory H2 database. You may want to:

 - [[Add a PostgreSQL service]] and
 - [[Bind to a PostgreSQL service]]
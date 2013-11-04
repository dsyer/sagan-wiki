### Goal

Get the Sagan web app up and running under your own Cloud Foundry account.

### Prerequisites

1. [[Get started with Cloud Foundry]]
1. [[Get the code]]

### Steps

#### Build the executable sagan-site JAR

    $ cd $SAGAN_HOME/sagan-site
    $ ../gradlew build -x check

> **Note:** When the above is complete, you will find the JAR file at `build/libs/sagan-site.jar`

#### Push the site to Cloud Foundry

In the command below, you will provide a `--host` argument, which will be used to form the URL `http://[host].cfapps.io`. The recommended host naming scheme is `$GHUSER-sagan`, where `$GHUSER` is your personal GitHub username. This approach helps avoid naming conflicts with other users who are deploying the Sagan app to Cloud Foundry under the shared `cfapps.io` domain. The host value of `cbeams-sagan` is used as an example below.

    $ cf push --start -m manifest/generic.yml --host cbeams-sagan

You should now see output similar to the following, as the app is uploaded and started:

    Using manifest file manifest/generic.yml

    Creating sagan... OK
    Binding cbeams-sagan.cfapps.io to sagan... OK
    Uploading sagan... OK
    Preparing to start sagan... OK
    -----> Downloaded app package (60M)
    Initialized empty Git repository in /tmp/buildpacks/java-buildpack/.git/
    -----> Downloading OpenJDK 1.7.0_45 from http://download.pivotal.io.s3.amazonaws.com/openjdk/lucid/x86_64/openjdk-1.7.0_45.tar.gz (1.1s)
           Expanding JRE to .java (1.0s)
    -----> Downloading Spring Auto-reconfiguration 0.7.2 from http://download.pivotal.io.s3.amazonaws.com/auto-reconfiguration/auto-reconfiguration-0.7.2.jar (0.1s)
    -----> Uploading droplet (90M)
    Checking status of app 'sagan'...
      1 of 1 instances running (1 running)
    Push successful! App 'sagan' available at http://cbeams-sagan.cfapps.io


#### Explore the running site

You should now be able to visit the site at http://[host].cfapps.io and browse around. You will notice that search functionality does not yet work and that the blog and team pages are empty.


### Next steps

At this point, the app is running against an in-memory H2 database. You may want to [[bind to a PostgreSQL DB on Cloud Foundry]].

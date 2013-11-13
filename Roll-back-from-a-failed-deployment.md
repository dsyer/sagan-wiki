### Two kinds of 'failure'

1. Actual CF routing issues

The deployment process appears to succeed, but you actually see 404s from the CF Router. This is extremely rare, but has been seen a couple of times. Two solutions:

 - re-run the deployment, i.e. click “Run” on the [sagan build plan](https://build.springsource.org/browse/IO-SAGANPROD)
 - re-map urls to the previous blue/green app (see below)

2. Successful deploy of problematic code

i.e. it deployed fine, but there’s something wrong in production—site doesn’t render properly, 500 errors, etc.

 - you could re-map urls (see below), but chances are the better approach is simply to:
 - fix the issue and re-deploy. Recommended approach here is to `git revert` the offending commits and push to master.


### re-map urls

The sagan app is deployed to production with the command 

    gradle deployProduction

Under the covers, this execs the

     sagan-site/scripts/deploy.sh

shell script which, upon successful deployment, invokes

     sagan-site/scripts/mapping-blue-green.sh

This script can be run on its own in order to ‘roll back’ a deployment, i.e. to revert to the previous blue/green pair.

Step 1: determine which variant of the app is currently live, e.g.:

    $ curl -I spring.io | grep spring-
    X-Application-Context: sagan-green:3

Looks like sagan-green is live. Therefore, we want to switch to sagan-blue.

    $ ./sagan-site/scripts/mapping-blue-green.sh production cf sagan-green sagan-blue

This will flip the live application to the previous version still running at sagan-blue.

This can be verified with the same curl command:

    $ curl -I spring.io | grep spring-
    X-Application-Context: sagan-blue:2

## For deploying to Cloud Foundry

Because we run spring.io on Cloud Foundry, we've documented the process for doing that here. But note that the Sagan
application is *just an executable JAR file* – this means it can run virtually anywhere!

### Platform

Deployment scripts are currently implemented in Bash, so in order to take full advantage,
you'll need to be running OS X, any other modern *nix, or Cygwin on Windows.

### Cloud Foundry command line interface

Install the `cf` [ruby client](http://docs.cloudfoundry.com/docs/using/managing-apps/cf/).

### Cloud Foundry account

You'll need a Cloud Foundry instance to deploy to. For those not already running Cloud Foundry on-premise, you can
easily [create an account](https://console.run.pivotal.io/register) on the public Cloud Foundry instance at [run
.pivotal.io](http://run.pivotal.io).

### Cloud Foundry space

You'll also need at least one Cloud Foundry space

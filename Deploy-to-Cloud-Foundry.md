### Requirements

#### 1. A Cloud Foundry account

You'll need a Cloud Foundry instance to deploy to. For those not already running Cloud Foundry on-premise, you can easily [create an account](https://console.run.pivotal.io/register) on the public Cloud Foundry instance at [run.pivotal.io](http://run.pivotal.io).

By default, you'll be set up with three Cloud Foundry [spaces](http://docs.cloudfoundry.com/docs/using/managing-apps/orgs-and-spaces.html). We'll assume deployment to the 'development' space for the remainder of this tutorial, but the instructions apply for staging, production, or any other space you may wish to create.

#### 2. Cloud Foundry command line interface

Install the `cf` [ruby client](http://docs.cloudfoundry.com/docs/using/managing-apps/cf/).

#### 3. A clone of the Sagan application

Follow the [Quick Start](https://github.com/cbeams/spring.io#quick-start--build-and-run-the-app-locally) instructions in the README of the Sagan repository.


### Steps

#### Create a manifest file
```
---
applications:
- name: sagan
  memory: 2G
  instances: 1
  env:
    GITHUB_CLIENT_ID: 92d0b0a74ad6d5236e01
    SPRING_PROFILES_ACTIVE: staging
    ELASTICSEARCH_INDEX: sagan-development
  host: sagan-staging-blue
  domain: cfapps.io
  path: ../build/libs/sagan-site.jar
  buildpack: https://github.com/cloudfoundry/java-buildpack
```

#### Push the app

    ./gradlew build -x check
    cf push --no-start sagan

#### 1. Set up the CF environment
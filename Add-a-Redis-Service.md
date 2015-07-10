### Goal

Set up Redis as a service using the Redis Cloud provider available from the Cloud Foundry marketplace.

### Prerequisites

1. [[Run the site on Cloud Foundry]]

### Steps

> _**Note:** These steps assume use of the public Cloud Foundry instance at http://run.pivotal.io and its marketplace._

#### Add the Redis service

1. Visit the Cloud Foundry console at http://run.pivotal.io
1. Click on the space where the site is running per the prerequisites section
1. Click 'Add' in the Services section of the page
1. Click 'Plan Options' on the 'Redis Cloud' service
1. Select the service level (_30MB_ is fine to start).
1. Click 'Buy this Plan'
1. Name the instance 'sagan-cache'
1. Assign it to the correct space
1. Leave 'Bind to an App' default ('[do not bind this app]') in place.

### Next steps

 - [[Configure Marketplace services]], see "Bind the Sagan app to those services"

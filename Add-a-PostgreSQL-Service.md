### Goal

Set up Postgres as a service using the ElephantSQL provider available from the Cloud Foundry marketplace.

### Prerequisites

1. [[Run the site on Cloud Foundry]]

### Steps

> **NOTE**: These steps assume use of the public Cloud Foundry instance at http://run.pivotal.io and its marketplace.

#### Add the ElephantSQL service

1. Visit the Cloud Foundry console at http://run.pivotal.io
1. Click on the space where the site is running per the prerequisites section
1. Click 'Add' in the Services section of the page
1. Click 'Plan Options' on the 'elephantsql' service
1. Select the database level (_Turtle_ is fine to start, but _Panda_ or greater is required in order to [[export a PostgreSQL dump]] from production).
1. Click 'Buy this Plan'
1. Name the instance 'sagan-db'
1. Assign it to the correct space
1. Leave 'Bind to an App' default ('[do not bind this app]') in place.

### Next steps

 - [[Bind to a PostgreSQL service]]

### Goal

Enable the use of search functionality when running the Sagan app on Cloud Foundry.

### Background

Out of the box, an attempt to run searches on Cloud Foundry will fail, resulting in a 500 error. This is because the connection to the Elasticsearch server (which defaults to localhost:9200) is being refused.

### Prerequisites

1. [[Run the site on Cloud Foundry]]

### Steps

> _**Note:** These steps assume use of the public Cloud Foundry instance at http://run.pivotal.io and its marketplace._

#### Add a Redis Marketplace service

1. Visit the Cloud Foundry console at http://run.pivotal.io
1. Click on the space where the site is running per the prerequisites section
1. Click 'Add' in the Services section of the page
1. Click 'Plan Options' on the 'Searchly Elasticsearch' service
1. Select the service level. You can try things out with a _Starter instance_ with 5MB, but indexing all Sagan content (especially all blog posts and javadocs) can take up to 200-300MB.
1. Click 'Buy this Plan'
1. Name the instance 'sagan-search'
1. Assign it to the correct space
1. Choose your application in the 'Bind to an App' form.

#### Restart the app to pick up new properties

    $ cf restart $APP_NAME

#### Verify

The search page should show errors anymore, but results may be empty because nothing has been indexed so far!
Creating blog posts is a good way to get content indexed easily.

### Next steps

 - [[Run the search indexer on Cloud Foundry]]
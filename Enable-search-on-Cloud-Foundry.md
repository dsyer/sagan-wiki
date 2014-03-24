### Goal

Enable the use of search functionality when running the Sagan app on Cloud Foundry.

### Background

Out of the box, an attempt to run searches on Cloud Foundry will fail, resulting in a 500 error. This is because the connection to the Elasticsearch server (which defaults to localhost:9200) is being refused.

### Prerequisites

1. [[Run the site on Cloud Foundry]]
2. You must **either**:
    - [[Set up and initialize an Elasticsearch instance]], or
    - [[Have access to an existing Elasticsearch instance]]

### Steps

#### Add CF environment variables for Elasticsearch properties

Assuming that the site is already running on Cloud Foundry per the prerequisites section, you need only to add environment variables to override the default values:

    $ cf set-env --no-restart $APP_NAME ELASTICSEARCH_ENDPOINT $URL
    $ cf set-env --no-restart $APP_NAME ELASTICSEARCH_INDEX $INDEX

where `$APP_NAME` is whatever you specified when following the instructions to [[run the site on Cloud Foundry]] (likely "sagan"); and where `$URL` and `$INDEX` are the values determined in step 2. of the prerequisites section.

#### Restart the app to pick up new properties

    $ cf restart $APP_NAME

#### Verify

You should now be able to see results when issuing a search.

### See also

 - [[Run the search indexer on Cloud Foundry]]
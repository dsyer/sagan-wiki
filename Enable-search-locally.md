### Goal

Enable the use of search functionality when running the Sagan app locally.

### Background

Out of the box, an attempt to run searches locally, e.g. <http://localhost:8080/search?q=ApplicationContext> results in a 500 error.

This is because the connection to the Elasticsearch server (which defaults to localhost:9200) is being refused.

### Prerequisites

1. You must be able to [[run the site locally]]
2. You must **either**:
    - [[Set up and initialize an Elasticsearch instance]], or
    - [[Have access to an existing Elasticsearch instance]]

### Steps

#### Run the site locally with Elasticsearch properties

Run the site as per usual, supplying environment variables to override the Elasticsearch defaults:

    ELASTICSEARCH_ENDPOINT=$URL ELASTICSEARCH_INDEX=$INDEX gradle sagan-site:bootRun

where `$URL` and `$INDEX` above are the values determined in step 2 of the prerequisites section.

### See also

 - [[Run the search indexer locally]]
 - [[Enable search on Cloud Foundry]]

### Goal

Enable the use of search functionality when running the Sagan app locally.

### Background

Out of the box, an attempt to run searches locally, e.g. <http://localhost:8080/search?q=ApplicationContext> results in a 500 error.

This is because the connection to the Elasticsearch server is being refused. By 

### Prerequisites

1. You must be able to [[run the site locally]]
2. You must **either**:
    - [[Set up and initialize an Elasticsearch instance]], or
    - Ask <sagan-ops@gopivotal.com> for the production Elasticsearch URL and index name

### Steps

#### Run the site locally with Elasticsearch properties

    java -jar sagan-site.jar -Delasticsearch.client.endpoint=$URL -Delasticsearch.client.index=$INDEX

Where `$URL` and `$INDEX` are the values determined in step 2 of the prerequisites above.

### See also

 - [[Run the indexer locally]]
 - [[Enable search on Cloud Foundry]]

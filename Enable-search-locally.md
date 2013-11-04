### Goal

Enable the use of search functionality when running the Sagan app locally.

### Background

Out of the box, an attempt to run searches locally, e.g. <http://localhost:8080/search?q=ApplicationContext> results in a 500 error.

This is because the connection to the Elasticsearch server (which defaults to localhost:9200) is being refused.

### Prerequisites

1. You must be able to [[run the site locally]]
2. You must **either**:
    - [[Set up and initialize an Elasticsearch instance]], or
    - Ask <sagan-ops@gopivotal.com> for the production Elasticsearch URL and index name

### Steps

#### Run the site locally with Elasticsearch properties

Run the site as per usual (using `java -jar` or `gradle run` syntax), supplying -D system property flags to override the Elasticsearch defaults:

    java -DELASTICSEARCH_ENDPOINT=$URL \
         -DELASTICSEARCH_INDEX=$INDEX \
         -jar sagan-site/build/libs/sagan-site.jar

where `$URL` and `$INDEX` above are the values determined in step 2 of the prerequisites section.

> **NOTE**: it is important that the `-jar` option and its argument come *after* the `-D` flags. Otherwise, the `-D` flags will be treated as arguments to the application's `main` method.

### See also

 - [[Run the indexer locally]]
 - [[Enable search on Cloud Foundry]]
### Goal

Install and configure an ElasticSearch instance that will be used by sagan-site.

### Prerequisites

None.

### Steps

#### Install ElasticSearch

Download and extract [ElasticSearch binaries](http://www.elasticsearch.org/downloads/0-90-12/) into a directory.

> _**Note:** Sagan requires Elasticsearch 0.90.x to enable search_

    $ cd elasticsearch-0.90.12
    $ ./bin/elasticsearch -v
      Version: 0.90.12, Build: 26feed7/2014-02-25T15:38:23Z, JVM: 1.8.0

#### Install ElasticSearch plugins (optional)

You can locally install plugins that will help you to inspect indices and types.
The [elasticsearch-head plugin](http://mobz.github.io/elasticsearch-head/) is quite useful for this task.

    $ cd elasticsearch-0.90.12
    $ ./bin/plugin -install mobz/elasticsearch-head
      -> Installing mobz/elasticsearch-head...
      Trying https://github.com/mobz/elasticsearch-head/archive/master.zip...
      Downloading .......................................................DONE

The complete list of existing plugins is available on the [ElasticSearch website](http://www.elasticsearch.org/guide/en/elasticsearch/reference/current/modules-plugins.html#known-plugins)

#### Run ElasticSearch

    $ ./bin/elasticsearch -f

Check that the instance is running:

    $ curl http://localhost:9200
      {
        "ok" : true,
        "status" : 200,
        "name" : "High-Tech",
        "version" : {
          "number" : "0.90.12",
          "build_hash" : "26feed79983063ae83bfa11bd4ce214b1f45c884",
          "build_timestamp" : "2014-02-25T15:38:23Z",
          "build_snapshot" : false,
          "lucene_version" : "4.6"
        },
      "tagline" : "You Know, for Search"
     }

If the head plugin is installed, its UI is available here: <http://localhost:9200/_plugin/head/> 

#### Set up this ElasticSearch instance for Sagan

Now that the instance is running, go to your Sagan workspace and set up the Sagan index, types and mappings.

    $ cd ./sagan-site/scripts/
    $ ./recreate-elasticsearch-index.sh

      usage: ./recreate-elasticsearch-index.sh ENDPOINT INDEX

      where ENDPOINT is the path to the endpoint (when installed locally, http://localhost:9200)
        and INDEX is the name of the endpoint, e.g. 'sagan'
    $ ./recreate-elasticsearch-index.sh http://localhost:9200 sagan

Remember that you'll have to use both arguments as JVM env variables `ELASTICSEARCH_ENDPOINT` and `ELASTICSEARCH_INDEX` when [[running Sagan locally|Enable-search-locally#run-the-site-locally-with-elasticsearch-properties]].

### Goal

Install and configure an ElasticSearch instance that will be used by sagan-site.

### Prerequisites

1. [[Enable search locally]]

### Steps

#### Install ElasticSearch

Download and extract [ElasticSearch binaries](http://www.elasticsearch.org/download/) into a directory.

From, that directory:

    $ cd elasticsearch-0.90.9
    $ ./bin/elasticsearch -v
      Version: 0.90.9, Build: a968646/2013-12-23T10:35:28Z, JVM: 1.8.0-ea

#### Install ElasticSearch plugins (optional)

You can locally install plugins that will help you to inspect indices and types.
The [elasticsearch-head plugin](http://mobz.github.io/elasticsearch-head/) is quite useful for this task.

    $ cd elasticsearch-0.90.9
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
        "name" : "Maria Hill",
        "version" : {
          "number" : "0.90.9",
          "build_hash" : "a968646da4b6a2d9d8bca9e51e92597fe64e8d1a",
          "build_timestamp" : "2013-12-23T10:35:28Z",
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

      where ENDPOINT is the path to the qbox.io endpoint (or http://localhost:9200)
        and INDEX is the name of the endpoint, e.g. 'sagan-production'
    $ ./recreate-elasticsearch-index.sh http://localhost:9200 sagan-dev

Remember that you'll have to use both arguments as JVM env variables `ELASTICSEARCH_ENDPOINT` and `ELASTICSEARCH_INDEX` when [[running Sagan locally|Enable-search-locally#run-the-site-locally-with-elasticsearch-properties]].
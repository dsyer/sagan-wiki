### Goal

Use an existing ElasticSearch instance with a Sagan application

### Background

If [[running locally an Elasticsearch instance|Set up and initialize an Elasticsearch instance]] is perfectly fine for testing locally Sagan, more complex deployments and search use cases require a dedicated ElasticSearch instance, or even cluster. 

### Prerequisites

1. [[Run the site locally]]

### Steps

#### Set up a dedicated ElasticSearch instance

ElasticSearch's website has [good documentation on how to set it up as a service](http://www.elasticsearch.org/guide/en/elasticsearch/reference/current/setup.html) on Linux or Windows. For production environments, relying on several instances (a cluster) is a good way to improve performance and reliability - but this is beyond the scope of this documentation. 

But you can also create a hosted ElasticSearch instance with existing providers, such as [qbox.io](http://qbox.io/).

Once this step is finished, you should have a URL for this new ElasticSearch.

> _**Note:** This URL should remain secret or better, should be protected by authentication/filtering since it gives a complete access to ElasticSearch features_

#### Configure this instance for Sagan

You should then configure this instance for Sagan, [[as described here|Set-up-and-initialize-an-elasticsearch-instance#set-up-this-elasticsearch-instance-for-sagan]].

#### Verify

You should now be able to see your instance and the configured index:

    $ curl http://search.example.org:9200/_status

    {
      "ok":true,
      "_shards":{"total":1,"successful":1,"failed":0},
      "indices":{
        // the name of your configured index
        "sagan":{
        // ...
        }
      }
    }

### Next steps

Remember that you'll have to use both the URL and the index name as JVM env variables ELASTICSEARCH_ENDPOINT and ELASTICSEARCH_INDEX in the next step:

 - [[Enable search locally]]
 - or [[Enable search on Cloud Foundry]]
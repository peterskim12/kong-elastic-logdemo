# kong-elastic-logdemo
Example of setting up Kong TCP Log plugin to log to Elastic

Run `docker-compose up` to spin up: Kong (db-less), Filebeat, Elasticsearch, and Kibana. 

Inspect the `kong.yml` declarative file to see:

-  A simple service and route set up for all requests to `/` go to `httpbin.org/anything`. 
- A tcp log plugin config to at the service level to send logs to `filebeat:9000`.

Kibana is available on `localhost:5601`.

`kibana.ndjson` is a Kibana Saved Objects file that contains a Kibana index pattern and dashboard configuration to help you get started quicker on viewing Kong logs in Kibana. See the [Kibana Saved Objects guide](https://www.elastic.co/guide/en/kibana/current/managing-saved-objects.html) to learn how to import the `.ndjson` file. Thanks to [Christoph Wurm](https://github.com/cwurm) for creating this great Kibana dashboard! 
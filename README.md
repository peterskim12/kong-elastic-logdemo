# kong-elastic-logdemo
Example of setting up Kong TCP Log plugin to log to Elastic

Inspect the `kong.yml` declarative file to see:

-  A simple service and route set up for all requests to `/` proxy to `httpbin.org/anything`. 
- A tcp log plugin config to at the service level to send logs to `filebeat:9000`.

# Start Kong and Elastic

1. Run `docker-compose up` to spin up: Kong (db-less), Filebeat, Elasticsearch, and Kibana. Kibana will be available on `localhost:5601`.

1. Import Kibana dashboard. `kibana.ndjson` is a Kibana Saved Objects file that contains a Kibana index pattern and dashboard configuration to help you get started quicker on viewing Kong logs in Kibana. See the [Kibana Saved Objects guide](https://www.elastic.co/guide/en/kibana/current/managing-saved-objects.html) to learn how to import the `.ndjson` file. Thanks to [Christoph Wurm](https://github.com/cwurm) for creating this great Kibana dashboard! 

1. Make requests to Kong. e.g. `curl -i localhost:8000/test`.

1. View Kibana dashboard. Load `Kong v2` Dashboard and see Kong data!


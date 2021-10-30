## Description
Analyzing Millions of NYC Parking Violations is about applying what I have learned about EC2, Docker, Elasticsearch and Kibana to a real-world dataset powered by NYC Open Data.

The python script runs in docker to get data from the Socrata Open Data API and then pushes that information into an Elasticsearch cluster provisioned via AWS.  After the data was loaded into the Elasticsearch cluster, visualizations are done in Kibana. I was able to load 18M+ rows using the Elasticsearch's BULK API.


## Technologies
Docker, Elasticsearch, Kibana, Python, AWS EC2, Terminal

## Usage
Step 1: Build the docker image 
```
docker build -t bigdata1:1.0 project01/
```
Step 2: Run the docker container 
```
docker run -v ${PWD}:/app -e DATASET_ID=“nc67-uf89” -e APP_TOKEN=“” -e ES_HOST=“” -e ES_USERNAME=“” -e ES_PASSWORD=“” bigdata1:1.0 --page_size=2 --num_pages=3
``` 
```--num_pages``` is optional

## References

 - [BULK API](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-bulk.html)
 - [Open Camera and Parking Violations API](https://dev.socrata.com/foundry/data.cityofnewyork.us/nc67-uf89)
 -   An [app token](https://data.cityofnewyork.us/profile/edit/developer_settings)  for the NYC Open Data API

## Kibana Dashboard

<img src="/project01/assets/kibanadashboard.png" width=1000>

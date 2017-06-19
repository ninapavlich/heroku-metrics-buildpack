# heroku-metrics-buildpack
Heroku buildpack for running Kibana 5, Logstash and ElastAlert


#Heroku + Elasticsearch Caveats:

1. I needed to adjust a few of my Kibana settings to properly to connect to Bonsai Elasticsearch:

server.host: "0.0.0.0"

# I needed to switch from https to http:
elasticsearch.url: "http://<BONSAI USERNAME>:<BONSAI PASSWORD>@<BONSAI SUBDOMAIN>.bonsaisearch.net"

# I needed to provide the username and password from the URL above:
elasticsearch.username: "<BONSAI USERNAME>"
elasticsearch.password: "<BONSAI PASSWORD>"

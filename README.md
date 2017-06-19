# heroku-metrics-buildpack
Heroku buildpack for running Kibana 5, Logstash and ElastAlert


## Installation Notes:

Specify a Kibana package version that matches the Elasticsearch version you're using:
> heroku config:set KIBANA_DOWNLOAD_URL="https://artifacts.elastic.co/downloads/kibana/kibana-5.1.1-linux-x86_64.tar.gz"

Optional: Specify a logstash package version. (2.3.1 will be used by default)
> heroku config:set LOGSTASH_DOWNLOAD_URL="https://download.elastic.co/logstash/logstash/logstash-2.3.1.tar.gz"

## Heroku + Elasticsearch Caveats:

I needed to adjust a few of my Kibana settings to properly to connect to Bonsai Elasticsearch:
	
	
	#Source: kibana.yml
	server.host: "0.0.0.0"

	# I needed to switch from https to http:
	elasticsearch.url: "http://<BONSAI USERNAME>:<BONSAI PASSWORD>@<BONSAI SUBDOMAIN>.bonsaisearch.net"

	# I needed to provide the username and password from the URL above:
	elasticsearch.username: "<BONSAI USERNAME>"
	elasticsearch.password: "<BONSAI PASSWORD>"

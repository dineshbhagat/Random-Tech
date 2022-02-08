Telegraf - Time-Series Data Collector   
InfluxDB - Time-Series Data Storage   
Chronograf - Time-Series Data Visualization   

Ref: 
- https://tianpan.co/notes/168-designing-a-metric-system  
- https://github.com/influxdata/telegraf
- https://www.influxdata.com/time-series-platform/telegraf/
- https://rootnroll.com/d/telegraf/
- https://v2.docs.influxdata.com/v2.0/get-started/

Installation: 

`brew install telegraf`


To have launchd start telegraf now and restart at login:  
  `brew services start telegraf`  
Or, if you don't want/need a background service you can just run:  
  `telegraf -config /usr/local/etc/telegraf.conf`  


`brew update;brew install influxdb;brew install kapacitor;brew install chronograf`

Info for influxdb
```bash
To have launchd start influxdb now and restart at login:
  brew services start influxdb
Or, if you don't want/need a background service you can just run:
  influxd -config /usr/local/etc/influxdb.conf
```

To integrate with grafana:
```bash
influx -precision rfc3339;
CREATE USER admin WITH PASSWORD 'admin' WITH ALL PRIVILEGES;
show users;
```

info for kapacitor and chronograf 
```bash
To have launchd start kapacitor now and restart at login:
  brew services start kapacitor
Or, if you don't want/need a background service you can just run:
  kapacitord -config /usr/local/etc/kapacitor.conf
  
To have launchd start chronograf now and restart at login:
  brew services start chronograf
Or, if you don't want/need a background service you can just run:
  chronograf
```
chronograf: http://localhost:8888


Ref: https://v2.docs.influxdata.com/v2.0/reference/api/

Default port(TCP) for influxdb:9999

https://docs.influxdata.com/influxdb/v1.7/introduction/getting-started/

----

To read messages from statsd

`nc -luv 8125`

8125 -> port at which statsd is running

----
How do you read metrics and what it means?

Ref: https://instrumentalapp.com/docs/instrumentald/system-metrics

https://github.com/influxdata/telegraf/tree/master/plugins/inputs/cpu

https://github.com/influxdata/telegraf/tree/ee056278f5e5860c252be4731280f75c91a40bc0/plugins/inputs


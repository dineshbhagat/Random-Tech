Telegraf - Time-Series Data Collector
InfluxDB - Time-Series Data Storage

Ref:  
- https://github.com/influxdata/telegraf
- https://www.influxdata.com/time-series-platform/telegraf/
- https://rootnroll.com/d/telegraf/

Installation: 

`brew install telegraf`


To have launchd start telegraf now and restart at login:  
  `brew services start telegraf`
Or, if you don't want/need a background service you can just run:  
  `telegraf -config /usr/local/etc/telegraf.conf`



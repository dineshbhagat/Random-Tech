Telegraf - Time-Series Data Collector   
InfluxDB - Time-Series Data Storage   
Chronograf - Time-Series Data Visualization   

Ref:  
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


`brew update;brew install influxdb;brew install chronograf`



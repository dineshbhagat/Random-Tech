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

Info for influxdb
```bash
To have launchd start influxdb now and restart at login:
  brew services start influxdb
Or, if you don't want/need a background service you can just run:
  influxd -config /usr/local/etc/influxdb.conf
```

info for chronograf and kapacitor
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

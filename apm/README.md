# Random-Tech


Ref:

https://stackshare.io/

https://www.metricfire.com/blog/prometheus-vs-influxdb/

https://prometheus.io/docs/introduction/comparison/


| statsd(Monitoring tools)                                     | telegraf(Monitoring tools or data collector)                 | graphite(time-series database)                               | prometheus(open-source monitoring tool and time-series database) | influxDB(**Databases**)                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| is a network daemon that runs on the Node.js platform and listens for statistics, like counters and timers, sent over UDP and sends aggregates to one or more pluggable backend services(e.g., Graphite) | *The plugin-driven server agent for collecting & reporting metrics* | Carbon is the primary backend daemon of Graphite.            | can be [integrated](https://prometheus.io/docs/instrumenting/exporters/) with many other different systems (for example, Docker, StatsD, MySQL, Consul, etc.) | *distributed time series database with no external dependencies* |
| *for easy stats aggregation*                                 | It is an agent for collecting, processing, aggregating, and writing metrics | developed in Python                                          |                                                              | scalable datastore for metrics, events, and real-time analytics |
| a front-end proxy for the Graphite/Carbon metrics server     |                                                              |                                                              |                                                              | Time-Centric Functions,Scalable Metrics, Events              |
| buckets: Each stat is in its own "bucket". They are not predefined anywhere. Buckets can be named anything that will translate to Graphite (periods make folders, etc),<br />values: Each stat will have a value. How it is interpreted depends on modifiers. In general values should be integer.<br />flush: After the flush interval timeout (defined by config.flushInterval, default 10 seconds), stats are aggregated and sent to an upstream backend service. |                                                              |                                                              | **Data model / storage:**<br />support multi-dimensional data, using labels<br />This allows easy filtering, grouping, and matching by these labels via the query language<br />can write data with the millisecond resolution timestamps<br />uses an append-only file per time-series approach for storing data<br />Prometheus’ main data type is float64 (however, it has limited support for strings) | **Data model / storage:**<br />Like Prometheus, the InfluxDB data model has key-value pairs as labels, which are called tags. In addition, InfluxDB has a second level of labels called fields, which are more limited in use.<br />is more advanced in this regard and can work with even nanosecond timestamps.<br />uses [another method of storing](https://docs.influxdata.com/influxdb/v1.7/concepts/storage_engine/), that is considered better for working with events logging. InfluxDB uses a variant of a [log-structured merge tree for storage with a write ahead log](https://docs.influxdata.com/influxdb/v1.7/concepts/storage_engine/), sharded by time. This is much more suitable to event logging than Prometheus's append-only file per time series approach.<br />InfluxDB supports float64, int64, bool, and string data types.<br /> |
|                                                              |                                                              |                                                              | [PromQL](https://www.metricfire.com/blog/getting-started-with-promql). *avg(time_series_name)*, *time_series_name{labelname="public"}* | [InfluxQL](https://docs.influxdata.com/influxdb/v1.7/query_language/spec/). *SELECT MEAN("value") FROM "time_series_name"*, *SELECT "value" FROM "time_series_name" WHERE tag="public". |
|                                                              |                                                              | Graphite uses a passive model, in which the Carbon daemon passively listens for time-series data that must be pushed from the node/client being monitored. Data is stored in a simple backend database called Whisper, and graphs are rendered as needed using a basic Django web app.<br />However, Graphite can also be turned into an active collector of metrics using special integrations to enable a Prometheus-like pull mode. e.g. [collectd and statsd](https://www.metricfire.com/blog/collectd-vs-statsd/) | is developed to **pull metrics** periodically from the target system.<br />For similar situations, you can use [Prometheus push gateway](https://prometheus.io/docs/practices/pushing/) in situations where metrics cannot be pulled | InfluxDB expects that an application will be sending data to it. So, when working with InfluxDB, you should set up the target system to **push data** to the InfluxDB server |

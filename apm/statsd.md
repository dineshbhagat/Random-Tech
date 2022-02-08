
```bash
brew install node
git clone https://github.com/etsy/statsd.git
cd statsd
cp exampleConfig.js config.js
```

- Edit `config.js`: Change `graphiteHost` to `localhost`.
- Optionally add debug options shown below.

Your `config.js` should look similar to this:

```
{
  graphitePort: 2003
, graphiteHost: "localhost"
, port: 8125
, backends: [ "./backends/graphite", "./backends/console" ] // console is for debug
, debug: true // For debug
, dumpMessages: true
, graphite: { legacyNamespace: false } // Better group all collected metrics under stats
}
```

Now you can run the statsd server:

```
node stats.js config.js
```

Ref: 
https://gist.github.com/tierra/aa8bb18ce04b4d055593

https://eureka.ykyuen.info/2014/08/22/statsd-installation-and-integration-with-graphite/

https://github.com/statsd/statsd/wiki#client-implementations



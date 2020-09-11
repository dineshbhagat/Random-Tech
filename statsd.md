
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
, backends: [ "./backends/graphite" ]
, debug: true
, dumpMessages: true
}
```

Now you can run the statsd server:

```
node stats.js config.js
```

Ref: https://gist.github.com/tierra/aa8bb18ce04b4d055593

Install grafana via homebrew/standalone  
`brew install grafana`
or  
`wget https://dl.grafana.com/oss/release/grafana-6.4.1.darwin-amd64.tar.gz`

```shell
# To have launchd start grafana now and restart at login:
  brew services start grafana
# Or, if you don't want/need a background service you can just run:
grafana-server --config=/usr/local/etc/grafana/grafana.ini --homepath /usr/local/share/grafana --packaging=brew cfg:default.paths.logs=/usr/local/var/log/grafana cfg:default.paths.data=/usr/local/var/lib/grafana cfg:default.paths.plugins=/usr/local/var/lib/grafana/plugins
```

http://localhost:3000,
admin
admin


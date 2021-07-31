***MQTT Commands from Command Line***

Subscribe
```bash
mosquitto_sub -h localhost -u USER -P PASSWORD -t '#'
```

Publish
```bash
mosquitto_pub -h localhost -t  channel/subChannel -m "message"  -r -q 2 -u "username" -P "password"
```

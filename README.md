Elasticfeed Plugins
===================

Build
-----
You need to get latest version of `elasticfeed` to build plugin.
```
  go get github.com/feedlabs/elasticfeed
```

Clients
-------
Create directory for your plugin definition by category e.g. `sensor/weather-on-mars`

Servers
-------
Create directory for your plugin server definition e.g. `plugins/sensor-weather-on-mars`
```go

package main

import (
  "github.com/feedlabs/elasticfeed/plugin"
  sensor "github.com/feedlabs/elasticfeed-plugin/sensor/weather-on-mars"
)
  
func main() {
	server, err := plugin.Server()
	if err != nil {
		panic(err)
	}
	server.RegisterPipeline(new(sensor.Sensor))
	server.Serve()
}

```

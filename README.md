# Shelly Exporter

A Prometheus exporter for Shelly Devices. Possibly useful to other home automation nerds, who are also observability nerds, who also own [Shelly](https://shelly.cloud/) devices.

Built with nodejs, using the [shellies](https://github.com/alexryd/node-shellies) library. Communicates with both CoAP and HTTP.

## Usage

```console
$ # Start shelly_exporter, and listen on 8177 for Prometheus metrics...
$ ./shelly_exporter -p 8177 &
Discovered device with ID A4CF12F3.... and type SHSW-1
Discovered device with ID A4CF12F4.... and type SHSW-1
Discovered device with ID 40F52001.... and type SHSW-PM
...
$ curl localhost:8177/metrics
# HELP shelly_relay relay
# TYPE shelly_relay gauge
shelly_relay{device_id="A4CF12F3....",device_type="SHSW-1",id="0"} 0
shelly_relay{device_id="A4CF12F4....",device_type="SHSW-1",id="0"} 0
shelly_relay{device_id="40F52001....",device_type="SHSW-PM",id="0"} 1

# HELP shelly_input input
# TYPE shelly_input gauge
shelly_input{device_id="A4CF12F3....",device_type="SHSW-1",id="0"} 0
shelly_input{device_id="A4CF12F4....",device_type="SHSW-1",id="0"} 0
shelly_input{device_id="40F52001....",device_type="SHSW-PM",id="0"} 0


# HELP shelly_power_watts power_watts
# TYPE shelly_power_watts gauge
shelly_power_watts{device_id="40F5200....",device_type="SHSW-PM",id="0"} 865.91

# HELP shelly_energy_counter_watt_minutes energy_counter_watt_minutes
# TYPE shelly_energy_counter_watt_minutes gauge
shelly_energy_counter_watt_minutes{device_id="40F52001....",device_type="SHSW-PM",id="0"} 512136
```

## LICENSE

Copyright 2021, Andrew Newdigate

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


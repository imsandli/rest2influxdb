# Introduction

This script reads values for a defined item from openHAB via the REST interface.
The values are written to text files and converted to a specific format to import them in InfluxDB2.
see: https://docs.influxdata.com/influxdb/v2.3/write_protocols/line_protocol_reference/

# Usage

Copy `config.cfg.example` to `config.cfg` and define your parameters like server name, user, password etc.

Start script
`./rest2influxdb.sh <Item_Name>`

Done.


# (un)known Issues

* Tested with openhab 3.3 and influx 2.3
* The timestamps cannot be calculated correctly on macOS
* RRD compresses data, so the further you go into the past the bigger gaps you get between two data points.  
see: https://github.com/openhab/openhab1-addons/wiki/rrd4j-persistence
* I am not sure if the defined timestamps are correct to read as much data as possible.


## Distributed monitoring 


### Node types
Types of nodes in a distributed environment:
- monitored node    - node under monitoring  
- aggregating node  - aggregates data from the monitored nodes  
- displaying node   - interogates the aggregating node and graphs the data in a relevant way

### Components

On each monitored node - a collectd service monitors selected parameters.
On the aggregating service - an influxdb database gathers data sent from all collectd processes.
The graphing service - Grafana queries influxdb and graphs data in a relevant way.

### Setup

On each monitored node:
- install collectd and use the shipped collectd.conf file

On the aggregating node:
- install collectd-influxdb-proxy from [collectd-influxdb-proxy]
- install influxdb 

On the graphing node:
- install grafana and start serving it via a web service


##### Note
The graphing and aggregating service can reside on the same node.


[collectd-influxdb-proxy]:https://github.com/ctradu/collectd-influxdb-proxy

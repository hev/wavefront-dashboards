# PKS Master Node Monitoring
This dashboard allows PKS Operators to manage master nodes by examaning etcd
metrics and infrastucture metrics from the node exporter. To configure 
PKS to export metrics to this dashboard input the following in the 
monitoring tab of the PKS tile.

```
[[outputs.wavefront]]
   token="<your-direct-ingest-token>"
   url="https://<your-instance>.wavefront.com"
[[processors.override]]         
  [processors.override.tags]
    director = "<your-director-name>"
```
The following are some ideas around monitoring master nodes.

## Quick Glance
How many clusters do you have and what are they called? The dashboard takes
advantage of the `cluster_name` tag and `etcd.server.guage.id` metric. 

## Leadership
Another concern for PKS operators is leadership election on Master

## Network and Disk "Pressure"
These "pressure" charts invert outbound network traffic and disk writes to
help operators visualize the shape of key usage.

## RPC
TBD

## Varibales
TBD 


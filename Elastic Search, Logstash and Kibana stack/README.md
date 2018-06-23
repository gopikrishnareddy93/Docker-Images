# Deploying Elastic Search, Kibana and logstash

This repository contains compose files to deploy elastic search, logstash and kibana onto your cluster. Currently I am pinning the stack to a node so that they all can share the same local volume. You can use nfs or ceph or any docker volume plugins of your choice to create persistant volumes and distribute the containers across the cluster.

The vm.max_map_count kernel setting needs to be set to at least 262144. To apply the setting on a live system type: sysctl -w vm.max_map_count=262144 or modify vm.max_map_count setting value in /etc/sysctl.conf to 262144 to make it permanent. 

# Command to deploy the stack
>modify the hostname in docker file before running the docker command

```sh
docker stack deploy -c docker-stack.yml elk-stack
```

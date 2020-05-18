* Take Ubuntu 18, with min of 8 GB RAM
Create Namespace
$  kubectl create namespace logging

$ kubectl apply -f elastic.yml -n logging
$ kubectl get all -n logging
$ kubectl get service -n logging
$ curl localhost:<servicePort#>
{
  "name" : "kqj_B3N",
  "cluster_name" : "docker-cluster",
  "cluster_uuid" : "iAfH-matTEyOV-BS28dtMw",
  "version" : {
    "number" : "6.5.4",
    "build_flavor" : "default",
    "build_type" : "tar",
    "build_hash" : "d2ef93d",
    "build_date" : "2018-12-17T21:17:40.758843Z",
    "build_snapshot" : false,
    "lucene_version" : "7.5.0",
    "minimum_wire_compatibility_version" : "5.6.0",
    "minimum_index_compatibility_version" : "5.0.0"
  },
  "tagline" : "You Know, for Search"


$  sync; echo 1 > /proc/sys/vm/drop_caches
$  sync; echo 2 > /proc/sys/vm/drop_caches

$ kubectl apply -f rbac.yml
$ kubectl apply -f fluentd.yml
$ kubectl get pods -n kube-system
$ kubectl logs -f fluentd-POD -n kube-system
 - check for "Connection opened to Elasticsearch cluster"
$ kubectl create -f kibana.yaml -n logging
$ kubectl get pods -n logging
$ kubectl get service -n logging
 - Add KIBANA_EXPOSED_PORT from the service to the Inbound rules	
 - Connect to kibana using: http://HOSTIP:KIBANA_EXPOSED_PORT

- Create a test pod 
- run this under Kibana -> Discover -> "kubernetes.pod_name:<podname>"

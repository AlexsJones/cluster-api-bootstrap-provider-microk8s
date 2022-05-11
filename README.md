## cluster-api-bootstrap-provider-microk8s


### Requirements

- Golang 1.17
- gcc
- Kind
- clusterctl
- kubectl

### Local (hacking) Development

1. Run a kind create cluster with the following config object

```
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  extraMounts:
    - hostPath: /var/run/docker.sock
      containerPath: /var/run/docker.sock
```

2. Install CAPI `clusterctl init --infrastructure docker`
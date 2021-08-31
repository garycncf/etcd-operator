# etcd-operator
```bash
oc new-project myproject
oc create -f etcd-operator-crd.yaml
oc create -f etcd-operator-sa.yaml
oc create -f etcd-operator-role.yaml
oc create -f etcd-operator-rolebinding.yaml
oc create -f etcd-operator-deployment.yaml
oc get pods
oc create -f etcd-operator-cr.yaml
oc get etcdclusters
oc get pods -l etcd_cluster=example-etcd-cluster -w
oc run etcdclient --image=busybox busybox --restart=Never -- /usr/bin/tail -f /dev/null
oc rsh etcdclient
$ wget https://github.com/coreos/etcd/releases/download/v3.1.4/etcd-v3.1.4-linux-amd64.tar.gz
$ tar -xvf etcd-v3.1.4-linux-amd64.tar.gz
$ cp etcd-v3.1.4-linux-amd64/etcdctl .
$ export ETCDCTL_API=3
$ export ETCDCTL_ENDPOINTS=example-etcd-cluster-client:2379
$ ./etcdctl put operator sdk
$ ./etcdctl get operator
$ exit
export EXAMPLE_ETCD_CLUSTER_POD=$(oc get pods -l app=etcd -o jsonpath='{.items[0].metadata.name}')
oc delete pod $EXAMPLE_ETCD_CLUSTER_POD
```

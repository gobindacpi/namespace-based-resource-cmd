# namespace-based-resource-cmd
kubernetes namespace based all resource find command


find all resourse assigned for namespace of rook-ceph:
kubectl api-resources --verbs=list --namespaced -o name   | xargs -n 1 kubectl get --show-kind --ignore-not-found -n rook-ceph

[root@rook-ceph-tools-99779cb98-pc895 /]# ceph osd pool set gobinda size 1 --yes-i-really-mean-it
set pool 2 size to 1


[root@rook-ceph-tools-99779cb98-pc895 /]# ceph osd pool ls
device_health_metrics
kubernetes
.rgw.root
gobinda
mn

[root@rook-ceph-tools-99779cb98-pc895 /]# rbd ls gobinda
csi-vol-6b8d2de0-46a3-11ec-aab7-d6f74e7308a0
csi-vol-88badf0b-46a3-11ec-aab7-d6f74e7308a0
csi-vol-cae2225c-46a2-11ec-aab7-d6f74e7308a0


 alias k='kubectl get pod -n rook-ceph'


kubectl -n rook-ceph get secret rook-ceph-dashboard-password -o jsonpath="{['data']['password']}" | base64 --decode && echo

```
$ kubectl api-resources | grep ceph
cephblockpools                                 ceph.rook.io                   true         CephBlockPool
cephclusters                                   ceph.rook.io                   true         CephCluster
cephfilesystems                                ceph.rook.io                   true         CephFilesystem
cephnfses                         nfs          ceph.rook.io                   true         CephNFS
cephobjectstores                               ceph.rook.io                   true         CephObjectStore
cephobjectstoreusers                           ceph.rook.io                   true         CephObjectStoreUser
```
```
$ kubectl get ns
NAME              STATUS   AGE
default           Active   55m
kube-node-lease   Active   55m
kube-public       Active   55m
kube-system       Active   55m
rook-ceph         Active   28m
```
```
$ kubectl get all -n rook-ceph
NAME                                                READY   STATUS      RESTARTS   AGE
pod/csi-cephfsplugin-876bf                          3/3     Running     0          31m
pod/csi-cephfsplugin-provisioner-544f9dd444-85m28   4/4     Running     0          31m
pod/csi-cephfsplugin-provisioner-544f9dd444-k5glq   4/4     Running     0          31m
pod/csi-rbdplugin-fmh4q                             3/3     Running     0          31m
pod/csi-rbdplugin-provisioner-65cd8687d9-j8lwz      5/5     Running     0          31m
pod/csi-rbdplugin-provisioner-65cd8687d9-jvqb6      5/5     Running     0          31m
pod/rook-ceph-mds-myfs-a-566586bc7f-pj9jc           1/1     Running     0          29m
pod/rook-ceph-mds-myfs-b-66fbcf5db7-6lwdc           1/1     Running     0          29m
pod/rook-ceph-mgr-a-749bfdcb-wrjgm                  1/1     Running     0          30m
pod/rook-ceph-mon-a-9b8cd79b-6cr65                  1/1     Running     0          30m
pod/rook-ceph-operator-64c69f5d9-nsp57              1/1     Running     0          31m
pod/rook-ceph-osd-0-6f65f74dc8-279px                1/1     Running     0          29m
pod/rook-ceph-osd-prepare-node01-hmkb8              0/1     Completed   0          29m
pod/rook-ceph-tools-58b6c58d6-dbxwf                 1/1     Running     0          31m
pod/rook-discover-r2sfz                             1/1     Running     0          31m

NAME                               TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)             AGE
service/csi-cephfsplugin-metrics   ClusterIP   10.99.18.161     <none>        8080/TCP,8081/TCP   31m
service/csi-rbdplugin-metrics      ClusterIP   10.104.175.29    <none>        8080/TCP,8081/TCP   31m
service/rook-ceph-mgr              ClusterIP   10.103.208.234   <none>        9283/TCP            29m
service/rook-ceph-mgr-dashboard    ClusterIP   10.104.37.173    <none>        8443/TCP            29m
service/rook-ceph-mon-a            ClusterIP   10.102.64.46     <none>        6789/TCP,3300/TCP   30m
service/rook-ceph-rgw-my-store     ClusterIP   10.111.124.249   <none>        80/TCP              29m

NAME                              DESIRED   CURRENT   READY   UP-TO-DATE   AVAILABLE   NODE SELECTOR   AGE
daemonset.apps/csi-cephfsplugin   1         1         1       1            1           <none>          31m
daemonset.apps/csi-rbdplugin      1         1         1       1            1           <none>          31m
daemonset.apps/rook-discover      1         1         1       1            1           <none>          31m

NAME                                           READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/csi-cephfsplugin-provisioner   2/2     2            2           31m
deployment.apps/csi-rbdplugin-provisioner      2/2     2            2           31m
deployment.apps/rook-ceph-mds-myfs-a           1/1     1            1           29m
deployment.apps/rook-ceph-mds-myfs-b           1/1     1            1           29m
deployment.apps/rook-ceph-mgr-a                1/1     1            1           30m
deployment.apps/rook-ceph-mon-a                1/1     1            1           30m
deployment.apps/rook-ceph-operator             1/1     1            1           31m
deployment.apps/rook-ceph-osd-0                1/1     1            1           29m
deployment.apps/rook-ceph-tools                1/1     1            1           31m

NAME                                                      DESIRED   CURRENT   READY   AGE
replicaset.apps/csi-cephfsplugin-provisioner-544f9dd444   2         2         2       31m
replicaset.apps/csi-rbdplugin-provisioner-65cd8687d9      2         2         2       31m
replicaset.apps/rook-ceph-mds-myfs-a-566586bc7f           1         1         1       29m
replicaset.apps/rook-ceph-mds-myfs-b-66fbcf5db7           1         1         1       29m
replicaset.apps/rook-ceph-mgr-a-749bfdcb                  1         1         1       30m
replicaset.apps/rook-ceph-mon-a-9b8cd79b                  1         1         1       30m
replicaset.apps/rook-ceph-operator-64c69f5d9              1         1         1       31m
replicaset.apps/rook-ceph-osd-0-6f65f74dc8                1         1         1       29m
replicaset.apps/rook-ceph-tools-58b6c58d6                 1         1         1       31m

NAME                                     COMPLETIONS   DURATION   AGE
job.batch/rook-ceph-osd-prepare-node01   1/1           10s        29m
```

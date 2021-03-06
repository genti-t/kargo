Travis CI test matrix
=====================

GCE instances
-------------

Here is the test matrix for the Travis CI gates:

|           Network plugin|                  OS type|               GCE region|             Nodes layout|
|-------------------------|-------------------------|-------------------------|-------------------------|
|                    canal|       debian-8-kubespray|             asia-east1-a|                  default|
|                   calico|       debian-8-kubespray|        asia-northeast1-b|                  default|
|                  flannel|                 centos-7|           europe-west1-c|                  default|
|                   calico|                 centos-7|            us-central1-b|                  default|
|                    weave|                   rhel-7|               us-east1-c|                  default|
|                    canal|            coreos-stable|               us-west1-b|                  default|
|                    canal|                   rhel-7|           europe-west1-c|                 separate|
|                    weave|       ubuntu-1604-xenial|           europe-west1-d|                 separate|
|                   calico|            coreos-stable|            us-central1-f|                 separate|

Where the nodes layout `default` is that is given in the example inventory file.
And the `separate` layout is when there is only node of each type, which is a kube master,
compute and etcd cluster member.

Note, the canal network plugin deploys flannel as well plus calico policy controller.

Hint: the command
```
bash scripts/gen_matrix.sh
```
will (hopefully) generate the CI test cases from the current ``.travis.yml``.



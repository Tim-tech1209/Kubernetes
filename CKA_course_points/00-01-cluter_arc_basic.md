Basics
## work nodes -> host app as containers
## master nodes -> manage, plan, schedule and monitor nodes.
* ETCD cluster —> it stores the information about the cluster. key: value / what container is on what node, what time.
* kube scheduler -> scheuling applications and contains on nodes. identify the right node to place the container on, based on the container's resource requirements, the worker nodes capacity, or any other policies or constains.
* different offices is assigned for special tasks, such as the operation teams take cares of ship handling and traffic control. the cargo teams takes care of containers, once a container is damaged or destroyed, they make sure that new containers are available. the services team take care of IT and communications between different ships.
* controller-manager
* node-controller: they are responsible for onboarding new nodes to the cluster, handling situations when contain is not available or get destroyed.
* replication-controller: enable that the desirable numbers of containers are running at all times in replication group.

## how does one office reach the other office, and who manage them on a high level.
*kuber-apiserver: is responsible for orchestrating all operations within the cluster. it exposes the kubernetes' api, which is used by external users to perform management operations on the cluster. as well as the various controllers to monitor the status of the cluster and make necessary changes when required. and by the worker nodes to communicate with the server.

## runtime
docker, cotainerd, rkt

## let's turn our focus on the cargo ships.
* kubelet: every ship has a captain. captain is responsible for all the activities on the ships. the captain is responsible for liasing the master ships, starting to let the master ship know that they are insterested in joining the group, receiving about the information of the containers to be loaded on the ship, and loading the proper containers as required, sending the report back to the master about the status of this ship and the status of the containers on the ship, etc. the captain of the ship is the kubelet on the kubernetes.
a kubelete is an agent running on each node on the cluster. it listens for instructions from the kube-apiserver, and deploys, destroys containers on the nodes as required.
the kube-apiserver periodically fetchs the reports from kubelets to monitor the status of the nodes and containers on them.
* kube-proxy: it ensures that the necessary rules are in place on the worker nodes to allow the containers running on them to reach each other.





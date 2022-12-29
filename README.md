# k8s-practice-files
A repo used for k8s codes and services practice

#### Aure DevOps
- container runtime e.g. docker runs in every master and worker node

- Etcd is nothing but consistently and highly available Key value store used as a Kubernetes backing store for all cluster data.

- Scheduler is responsible for distributing containers across multiple nodes. Watches for newly created pods without an assigned node and selects a node to run on.

- Kube ApiServer acts as the frontend for the kubernetes control plane. It exposes the Kubernetes API so commandline tools like kubectl can communicate wit the control plane and kubelet.

- Kube Controller Manager holds the kube controllers. Controller are responsible for noticing when endpoints or container go down. controller like replication controller (manages replicas), endpoint controller, service account, token controller and many more.

- Kubelet is responsible for making sure that containers are running in a pod on a node and always in constant communication with the kube scheduler.

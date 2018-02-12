#  Kube-Circles
## Kubernetes the long way

Kube-Circles is the sets of very simple Ansible playbooks for rapid deployment of small production or lab Kubernetes High Available Cluster.
With this project you also can learn Kubernetes from simplest to more complicated setups.

## Main features
- HA from the box
- Minimalistic configuration using one simple inventory YAML file only.
- No kubeadm, no containerized control-plane, no any sort of magic and spells.
- Automated cert generation and deployment.

## Circle 0

- CentOS distro based
- CentOS standard repository based
- No RBAC
- Insecure

## Usage
You need a set of the virtual or hardware servers, preconfigured for ssh passwordless access, with CentOS 7 installed and Ansible.
- Configure inventories/k8s-cluster inventory file with control-plane and worker nodes IP addresses and hostnames.
- Configure inventories/k8s-cluster inventoryfile with Keepalived VIP for HA control-plane access.
- (Optional) Configure inventories/k8s-cluster inventory file with service networks.
- Run ansible-playbook -i inventory/k8s-cluster roles/k8s-circle-0.yml
- Test you new cluster

## Backlog
- Multiple fixes and improvements
- Google Kubernetes repository-based deployment
- Secure deployment
- Multidistro deployment
- Load Balancing instead of the Keepalived

![Kube-scr](/images/kube.jpeg?raw=true "Running cluster")

## Based on
- http://www.tothenew.com/blog/how-to-setup-kubernetes-master-ha-on-centos/ blog
- https://github.com/kelseyhightower/kubernetes-the-hard-way/ How-to

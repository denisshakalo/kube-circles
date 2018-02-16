#  Kube-Circles
## Kubernetes the long way

Kube-Circles is the set of very simple Ansible playbooks for rapid deployment of small production or lab Kubernetes bare-metal High Available Cluster.
With this project you also can learn Kubernetes bare-metal architecture deployment from simplest to more complicated setups.

## Main features
- HA from the box
- Extremely easy configuration using one simple inventory YAML file only.
- No kubeadm, no containerized control-plane, no any sort of magic and spells.
- Automated cert generation and deployment.

## Circle 0

- CentOS distro based
- CentOS standard repository based
- No RBAC
- Insecure

## Usage
You need a set of  virtual or hardware servers, preconfigured for ssh passwordless access, with default minimal CentOS 7 configuration installed and Ansible.

In the inventories/k8s-cluster inventory file configure:
- Control-plane and worker nodes IP addresses, CIDR and hostnames
- Keepalived VIP {{api_server_vip}} for HA
- Custom service network CIDRs and SkyDNS ip (Optional)
- Run ansible-playbook -i inventory/k8s-cluster roles/k8s-circle-0.yml

Test the new cluster using http://{{api_server_vip}}:8080/ui/

## Backlog
- Multiple fixes and improvements
- Google Kubernetes repository-based deployment
- Secure deployment with RBAC
- Extended distro support


![Kube-scr](/images/kube.jpeg?raw=true "Running cluster")

## Based on
- http://www.tothenew.com/blog/how-to-setup-kubernetes-master-ha-on-centos/ blog
- https://github.com/kelseyhightower/kubernetes-the-hard-way/ How-to

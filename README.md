#  Kube-Circles
## Kubernetes the long way

Kube-Circles is the set of very simple Ansible playbooks for rapid deployment of small production or lab Kubernetes bare-metal High Available Cluster.
With this project you also can learn Kubernetes bare-metal architecture deployment from simplest to more complicated setups.

## Main features
- HA from the box
- Extremely easy configuration using one simple inventory YAML file only.
- No kubeadm, no containerized control-plane, no any sort of magic and spells.
- Automated cert generation and deployment.

## Circle 1 Release
- Google Kubernetes latest repository-based deployment
- Docker replaced by containerd
- Secure deployment with RBAC

## Circle 0 Release

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
- Run ansible-playbook -i inventory/k8s-cluster.yaml roles/k8s-circle-1.yml

Test the new cluster using http://{{api_server_vip}}:8080/ui/

## Backlog
- Addons
- Multiple fixes and improvements
- Cloud deployment
- Extended distro support


![Kube-scr](/images/kube.jpeg?raw=true "Running cluster")

## Based on
- https://www.ibm.com/support/knowledgecenter/en/SSMNED_5.0.0/com.ibm.apic.install.doc/tapic_install_Kubernetes.html IBM Knowledge Center
- https://github.com/kelseyhightower/kubernetes-the-hard-way/ Kubernetes The Hard Way

# Supported Linux Distributions
-   **Debian** Jessie, Stretch, Wheezy
-   **Ubuntu** 16.04

# Requirements
-   **Ansible v2.4+ and python-netaddr is installed on the machine
    that will run Ansible commands**
-   **The target servers must have access to the Internet**

# Quick Start
To deploy the cluster  :
```bash

# Edit Ansible inventory file  to suit your environment
$vim kubeadm-ansible/inventory/inventory

# Edit Ansible all.yml file  to  allow ansible to complete the kubernetes environment witch you want
$vim kubeadm-ansible/inventory/group_vars/all.yml

# Review  change parameters
$cat kubeadm-ansible/inventory/inventory
$cat kubeadm-ansible/inventory/group_vars/all.yml

#Deploy kubernetes cluster with Kubeadm Ansible Playbook
$ansible-playbook playbook/init.yml
```

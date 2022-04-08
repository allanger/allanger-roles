Kubeadm Ansible Role
=========

Init k8s cluster with Ansible using kubeadm. 
1. Install container runtime 
I Prefer containerd, but if you want, feel free to implement any other and open a PR
2. Install kubernetes packages
3. Init master node 
4. Join worker nodes

Role Variables
--------------
```
kubernetes_apiserver_advertise_address: ${MASTER_HOST_INTERNAL_ADDRESS}
kubernetes_control_plane_endpoint: ${MASTER_HOST_EXTERNAL_ADDRESS}
kubernetes_version: ${CLUSTER_VERSION}
kubelet_version: ${PACKAGE VERSION}
kubeadm_version: ${PACKAGE VERSION}
kubernetes_cluster_name: ${CLUSTER_NAME}
```
Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
# --------------------------------------
# -- Initialize kubernetes cluster
# --------------------------------------
---
- hosts: all
  become: yes
  roles:
    - role: '.'
      ansible_play_role_names: "install cluster with kubeadm"
```
License
-------

BSD

Author Information
------------------
Feel free to contribute

If you got something to say, send me an email (allanger@protonmail.com)

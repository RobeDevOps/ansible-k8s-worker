robedevops.ansible_k8s_worker
=========

It roles just add new k8s worker node to the cluster. The cluster was initialized by **robedevops.ansible_k8s_master**

Requirements
------------

N/A

Role Variables
--------------

N/A

Dependencies
------------

It role has dependencies on roles:

* [**robedevops.ansible_k8s_nodes**](https://github.com/RobeDevOps/ansible-k8s-nodes): Configure and install all the packages and tools required by k8s node.
* [**robedevops.ansible_k8s_master**](https://github.com/RobeDevOps/ansible-k8s-master): Creates the k8s master node.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- hosts: k8s-nodes
  gather_facts: yes
  become: yes
  roles:
    - { role: robedevops.ansible_docker, tags: ['docker'] }
    - { role: robedevops.ansible_docker_user, tags: ['docker-user'] }
    - { role: robedevops.ansible_k8s_nodes, tags: ['k8s-nodes'] }

- hosts: k8s-masters
  gather_facts: yes
  become: yes
  roles:
    - { role: ansible-k8s-master, tags: ['k8s-master'] }

- hosts: k8s-workers
  gather_facts: yes
  become: yes
  roles:
    - { role: ansible-k8s-worker, tags: ['k8s-worker'] }
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

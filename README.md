# Openshift-labeler

Playbook to label OpenShift nodes.

### Sample inventory
Your inventory should have groups of hosts describing the roles they play in the OpenShift cluster. This playbook looks for the following groups in the inventory file:
```
[controller]

[masters]

[nodes]

[etcd]

[lb]

[glusterfs]

```
Note: glusterfs group represents cns nodes.

### Run
```
$ ansible-playbook -i <inventory> label.yml
```
The playbook looks for kube config in Home directory and copies the config from one of the master node in case it doesn't find one.

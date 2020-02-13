# ocp-customization-plays
This is a collection of roles and playbooks to help cutomize OCP deployment including deploying a secured disconnected docker registry (docker-distribution), disabling IPv6 on all hosts if needed, setting MTU on the default IPv4 interface, using pood man DNS (i.e. update /etc/hosts file on all nodes) as well few other utilities like configuring the requestheader Identity provider on each of the masters as well as granting grapha visualization role to users. 
This has been tested on the 3.11 stream and will be updated for 4.x when available. 
It is also recommended to add openshift_node_sdn_mtu=1450 to the inventory file to control the MTU for each of the OCP node in addition to using the statis IP config playbook above to update the network file for each node to have the desired MTU. 

To install this first use ansible-galaxy to install dependencies like below:
```
ansible-galaxy install -r requirements.yml --roles-path=roles
```

# ansibletower_OCP-playbooks
Add nodes - https://docs.openshift.com/container-platform/3.9/install_config/adding_hosts_to_existing_cluster.html

## Add Nodes
add_nodes_part1.yml
* Add new host into `[new_nodes]`/`[new_masters]` in the inventory
* Creates host_vars file
add_nodes_part2.yml
* Remove new host from [`new_nodes]`/`[new_masters]` in the inventory
* Add new host into `[nodes]`/`[masters]` in the inventory

Requires:
* Ansible Tower up and running
* OCP up and running

### To Use
#### Configuration on Ansible Tower
##### Templates Tab
Job Template:
* add_nodes_part1.yml (survey)
* add_nodes_part2.yml
* scaleup.yml 

Workflow Template: <br />
`preflight -> add_nodes_part1.yml -> scaleup.yml -> add_nodes_part2.yml`

# ansibletower_OCP-playbooks
Add nodes - https://docs.openshift.com/container-platform/3.9/install_config/adding_hosts_to_existing_cluster.html

## Add Nodes
### add_nodes_part1.yml
* Add new host eitherinto `[new_nodes]` or `[new_masters]` in the inventory
* Creates host_vars file required for Ansible Tower to read the host
### add_nodes_part2.yml
* Move new host from [`new_nodes]` or `[new_masters]` to `[nodes]` or `[masters]` respectively in the inventory

## To Use
### Configuration on Ansible Tower
#### Templates Tab
Job Template:
* add_nodes_part1.yml (survey mode with `survey_var` = `node` or `master` and `fqdn` = `hostname`)
* add_nodes_part2.yml
* scaleup.yml 

Workflow Template: <br />
`preflight -> add_nodes_part1.yml -> scaleup.yml -> add_nodes_part2.yml`

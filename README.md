
# anspire
This is an effort to track de ansible files used to create a federated SPIRE/SPIFFE environment

## Getting Started
### Requirements

The ansible script assumes you have 4 hosts. These hosts must have their hostnames with FQDN properly configured and DNS entries must resolve on all hosts.

Also, there should be a bastion node with Ansible installed acting as the controller.
This bastion should be able to SSH into all servers using a trusted key pair and sudo without asking for password.

### Files

Inside the inventory file servers are nodes that will be configured as SPIRE Servers. It divides into two groups:
`domain1servers` and `domain2servers`. Inside either the FQDN of the servers or the IP is expected.

Both subgroups above are comprised of nodes from distinct domains that will be federated.

The domain FQDN is set using `domainfqdn` variable inside the invetory file itself.

Lastly the `nodes` is the group that will receive the SPIRE Agents. There are two subgroups: `domain1nodes` and `domain2nodes`. Inside either the FQDN of the nodes or the IP is expected for both domains.


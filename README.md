# Hetzner Swag provision with Ansible

## Description

These Ansible playbooks make it possible to deploy a virtual machine based on Debian at Hetzner. This with Docker, Swag, a wildcard.$domain.duckdns domain and reconized X509/TLS certificates.
Keep in account that you need to pay for the virtual machine at Hetzner.  The virtual machine is paid per hour and the ipv4 address per month. This script provisions the cheapest virtual machine currently offered at Hetzner.

Background information:
* https://www.hetzner.com/cloud
* https://docs.ansible.com/ansible/latest/collections/hetzner/hcloud/
* https://www.duckdns.org/
* https://docs.linuxserver.io/general/swag

Pricing:
* https://docs.hetzner.com/robot/general/pricing/hetzner-pricing/

Type of servers at Hetzner possible to be provisioned
* https://docs.hetzner.com/cloud/servers/overview

## prerequisites
### Workstation with the following software installed

- Pip3
- Ansible

### The following accounts and api tokens you need to have
- Hetzner account with a valid creditcard
- Hetzner api token
- Duckdns account with a registrated subdomain
- Duckdns api token

### Declared the following variables in vars/main.yml

- fqdn_duckdns: the subdomain registrated at Duckdns
- duckdnstoken
- hetzner_cloud_api_token: The Hetzner api token with read/write permissions
- ssh_develop_key: ssh pubkey from the ssh private key you're using
- ssh_develop_key_name: the name of the publickey i.e.: my_workstation

## How to provision
```
git pull git@github.com:maikell/Hetzner_swag_provision.git
cd Hetzner_swag_provision
ansible-playbook start.yml
```

## How to remove the  provisioned VM
```
cd Hetzner_swag_provision
ansible-playbook stop.yml
```

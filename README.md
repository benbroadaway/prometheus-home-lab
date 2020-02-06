# Homelab Grafana and Metrics Install

## What?

This repo installs Grafana and Prometheus for metrics collection in
a home lab. There's support for scraping [Concord](https://concord.walmartlabs.com) too!

## Configure It 

Update the inventory and vars (and vault) for whatever.

- `inventories/homelab.yml` - ansible inventory of hosts to monitor
- `playbook/group_vars/homelab/vars.yml` - Non-sensitive variables for the playbook
- `playbook/group_vars/homelab/vault.yml` - Sensitive variables, including ssh connection settings.

## Run it

```
ansible-playbook \
  -i ./inventories/homelab.yml \
  --vault-password-file ~/.vault_pass.txt \
  ./playbook/install.yml
```

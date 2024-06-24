# Brain-cockpit deployment scripts

This repo contains ansible playbooks used to deploy an instance of `brain-cockpit`.
It was used to deploy a working instance on:

- a TGCC virtual machine
- an EBRAINS virtual machine

In short, it does the following:

- sets up the virtual machine (software update)
- downloads and builds brain-cockpit
- sets up brain-cockpit as a `systemd` service
- checks that brain-cockpit's backend is started

## Quickstart

The following command runs the playbook from your local machine:

```bash
ansible-playbook -i inventory.yaml brain-cockpit-playbook.yaml
```

## VPN

You may need to use a correctly configured VPN to access EBRAINS machines.

```bash
ssh -o ProxyCommand='ssh -W %h:%p -i ~/.ssh/id_rsa.pub -q alexis@jh-1.tc.humanbrainproject.eu' alexis@brain-cockpit.jsccloud
```

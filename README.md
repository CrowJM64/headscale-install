# Ansible Role for Headscale Configuration
**Author/Maintainer:** Josh Murphy

## Overview
This Ansible role configures Head/TailScale by doing the below:
```yaml
- Installs the desired version of Headscale to the designated Headscale Server, running rootless under a headscale user.
- Provisions using LetsEncrypt, assuming the machine is publicly accessible on ports 443/tcp for Headscale serving and 80/tcp for LetsEncrypt communication.
- Creates the Headscale Group, and a PreAuthKey associated with that Group.
```

## Steps
```yaml
- Configure the below settings in the *headscale-config.yaml* template
  - server_url
  - acme_email
  - tls_letsencrypt_hostname
  - base_domain
  - search_domains
- Configure the below settings in the *acl.json* template
  - Groups
  - Access rules to tagged machines. 
```

## Supported Platforms and Derivatives
Below are the explicitly tested Distros.
```yaml
## Redhat
Rocky - 10, 9
Fedora - 44, 43
Oracle - 10, 9
AmazonLinux - 2027, 2023

## Debian
Debian - 13, 12
Ubuntu - 2604, 2404

## Suse
OpenSuse Leap - 15
```

## Example Playbook

```yaml
- hosts: all
  become: yes

  roles:
    - role: headscale-install
```

### From Ansible Galaxy

```bash
ansible-galaxy install crowjm64.headscale-install
```

This role was created and is maintained by **[CrowJM64](https://github.com/CrowJM64)**.
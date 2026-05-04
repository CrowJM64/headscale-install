# Ansible Role for Headscale Configuration
**Author/Maintainer:** Josh Murphy

## Overview

This Ansible role configures Head/TailScale by doing the below:
```yaml
- Installs the desired version of Headscale to the designated Headscale Server.
- Provisions using LetsEncrypt, assuming the machine is publicly accessible on 80+443/tcp
- Creates the Headscape Group, and a PreAuthKey associated with that Group.
- Installs Tailscale to the Clients connecting to the headscale server.
- Joins the Tailscale Client to the Headscale Server using the above PAK.
```

## Dependencies
- TBC

## Supported Platforms and Derivatives
Headscale is . Below are the explicitly tested Distros.
```yaml
## Headscale Server
Debian
Ubuntu

# RedHat
Rocky 10/9
CentOS 10/9
Fedora 43/42
Oracle 10

  # Debian
Ubuntu 24.04/22.04
Debian 13
Alma 10
Mint 22
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
ansible-galaxy install crowjm64.system_ssh_hardening
```

This role was created and is maintained by **[CrowJM64](https://github.com/CrowJM64)**.
# Ansible Role for Headscale Configuration
**Author/Maintainer:** Josh Murphy

## Overview

This Ansible role configures Head/TailScale by doing the below:
```yaml
- Installs the desired version of Headscale to the designated Headscale Server.
- Provisions using LetsEncrypt, assuming the machine is publicly accessible on 80+443/tcp
- Creates the Headscape Group, and a PreAuthKey associated with that Group.
- Opens port 443/tcp for Headscale serving and 80/tcp for LetsEncrypt communication. 
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
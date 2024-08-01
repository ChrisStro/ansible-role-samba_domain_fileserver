# Ansible Role: samba_domain_fileserver

Ansible role for active directory joined samba-fileserver

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):
```yaml
# this is only for quick labs
samba_dc_inventory_group: samba_domain_controller
samba_netbios_domainname: SAMBA
samba_domainname: SAMBA.LOCAL
samba_adminpwd: Start1234
```

## How to Inventory
You need a group for primary domain controller lookup via inventory file

```yaml
all:
  children:
    samba:
      children:
        samba_domain_controller: # lookup var samba_dc_inventory_group
          hosts:
            samba-dc:
        samba_domain_file_server:
          hosts:
            samba-fs:
        samba_standalone:
          hosts:
```

# VMware license management
Ansible roles that adds/removes licenses on vCenter Server

The configuration of the role is done so that it shouldn't be necessary to
modify the role for any configuration.
All settings can be configured by changing role parameters or by declaring new
config as variable.

Please report any issues or send PR.

## Examples
```yaml
---

- name: Example of how to add a couple licenses
  hosts: switches
    vars:
      vcenter_auth:
        hostname: 192.0.2.1
        username: administrator@abc.lan
        password: super_pass
        validate_certs: False

      vmware_license:
        - name: vcenter_server
          license: 00000-00000-00000-00000-00000
          state: present
          lables: ansible
        - name: vsphere
          license: 11111-11111-11111-11111-11111
          state: present
          lables: ansible          
  roles:
    - ansible-vmware_license  

  ```

## Role variables
```yaml
# ---------------------------------------------------------------------------
# Define the vcenter auth details to be used
# ---------------------------------------------------------------------------
vcenter_auth: { }


# ---------------------------------------------------------------------------
# Define the vmware license details to be added/removed
# ---------------------------------------------------------------------------
vmware_license: { }
```

## License
Apache

## Author
Dan Murarasu

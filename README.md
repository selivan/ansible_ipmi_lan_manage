# Ansible role to manage IPMI settings

Ansible role for managing IPMI LAN settings with [ipmitool](https://github.com/ipmitool/ipmitool). Local fact script in /etc/ansible/facts.d on remote host is created and used later.

This role needs to be run as root, so use it with `become: yes`.

## Variables

```yaml
get_ipmi: True  # Default: False
```

Query the current IPMI settings for each host and attempt to save them to `impi_host_settings_save_path` unless you already have ipmi: defined somewhere.

```yaml
impi_host_settings_save_path:
```

Path to save IMPI settings for host when `get_impi` is `True`.

```yaml
set_ipmi: True  # Default: False
```

By default this role will only report differences between saved and actual IPMI settings.  Use `-e "set_ipmi=True"` to "arm" ipmi and run the `ipmi lan set` commands if this settings differ.

Variables(usually those are host variables) used by `set_impi`:

- `ipmi.vlan`
- `ipmi.address`
- `ipmi.netmask`
- `ipmi.gw`

Only static IP address is supported.

**P.S.** If this code is useful for you - don't forget to put a star on it's [github repo](https://github.com/selivan/ansible_ipmi_lan_manage).

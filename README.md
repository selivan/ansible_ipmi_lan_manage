ansible_ipmi_lan_manage
=======================

Ansible role for managing IPMI LAN settings with ipmitool. Local fact in /etc/ansible/facts.d on remote host is created and used.

Run with the `-s / --sudo` option, needed for ipmitool to query successfully and consistently.

# Variables:

<dl>
<dt>
```bash
get_ipmi: True  # Default: False
```
</dt>
<dd>
Query the current IPMI settings for each host and attempt to save them to host_vars/{{inventory_hostname_short}}/ipmi
unless you already have ipmi: defined somewhere.
</dd>

<dt>
```bash
set_ipmi: True  # Default: False
```
</dt>
<dd>
By default this role will only report on differences.  Use `-e "set_ipmi=True"` to
"arm" ipmi and run the `ipmi lan set` commands if necessary.
</dd>
</dl>

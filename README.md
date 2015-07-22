ansible_ipmi_lan_manage
=======================

Ansible role for managing IPMI LAN settings with ipmitool. Local fact in /etc/ansible/facts.d on remote host is created and used.

Run with the -s / --sudo option, needed for ipmitool to query successfully and consistently.

# Variables:

Query the current IPMI settings for each host and attempt to save them to host_vars/{{ inventory_hostname_short }}/ipmi
unless you already ipmi: defined somewhere.

	get_ipmi: True  # Default: False

This role will only report on differences. Set this var to True to
"arm" ipmi and run the `ipmi lan set` commands if necessary.

	set_ipmi: True  # Default: False

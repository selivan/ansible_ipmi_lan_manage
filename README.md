ansible_ipmi_lan_manage
=======================

Ansible role for managing IPMI LAN settings with ipmitool. Local fact in /etc/ansible/facts.d on remote host is created and used.

Run with the -s / --sudo option, needed for ipmitool to query successfully and consistently.

# Variables:

Set to True to query the current IPMI settings for the host and save them to host_vars/ipmi
	get_ipmi: True  # Default: False

This role will only report on differences. Set this var to True to
"arm" ipmi and run the ipmi lan set commands if necessary .
	set_ipmi: True  # Default: False

# Ansible Role: bind9

Installs and configures bind9 DNS server on Ubuntu 18.04 servers.

## Requirements

This role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

    - hosts: nameservers
      roles:
        - role: vikiscripts.bind9
          become: yes

This role has variable dependencies on Inventory file as below (Please do not change group names i.e. `ns1, ns2, ns3`) 
```
[nameservers:children]
ns1
ns2
ns3

[ns1]
10.10.10.61 host_name=ns1.vikilabs.local ansible_dns_role=master

[ns2]
10.10.10.62 host_name=ns2.vikilabs.local ansible_dns_role=slave

[ns3]
10.10.10.63 host_name=ns3.vikilabs.local ansible_dns_role=slave
````


## Role Variables

Available variables are listed in default values (see `defaults/main.yml`):


## Example Playbook

    - hosts: nameservers
      become: yes
      vars_files:
        - vars/main.yml
      roles:
        - { role: vikiscripts.bind9 }


## License

MIT / BSD

## Author Information

This role was created in 2019 by Vikas Pandey

# Ansible Role: bind9

Installs and configures bind9 DNS server on Ubuntu 18.04 servers.

## Requirements

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

    - hosts: nameservers
      roles:
        - role: vikiscripts.bind9
          become: yes

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

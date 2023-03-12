sambadc role
============

This role only does two jobs:

 - Configure a pre-installed samba server to be a new Domain Controler (DC)
 - Or configure a pre-installed samba server to join to existent DC group
 
 This role does not do the following, but depends them to work:
 
 - Install samba
 - Configure resolv.conf

Said that, this role contains a lot of codes and ideas copied from another roles and were
grouped here to achieve a different approach to setup samba dc:


 - https://github.com/yamb00/ansible-role-samba
 - https://github.com/bertvv/ansible-role-samba
 - https://github.com/mrlesmithjr/ansible-samba
 - https://github.com/criecm/ansible-role-samba
 - https://github.com/gentoo-ansible/role-samba-dc
 - https://github.com/tschifftner/ansible-role-samba
 - https://github.com/jtyr/ansible-samba
 - https://github.com/raasss/ansible-role-samba
 - https://github.com/HiTechRabbit/secondary_dc_samba_ansible
 - https://github.com/darrylweaver/ansible-samba

Example Playbook
----------------

You should install samba before run this role:

    - hosts: servers
      roles:
         - marioqxx.install_samba

Usage
-----

Please see defaults/main.yml

TODO: Write README.


sambadc role
============

This role installs, provisions and configures a Samba Domain Controller (DC).
The DC may be provisioned as Primary DC or may joint an existing REALM.

This role does:

 - Install samba and related packages
 - Provisions a Primary DC or joins an existing DC
 - Configure the DC
 - Configure the DNS, supported are SAMBA_INTERNAL and BIND_DLZ
 - Create configured Users and Groups
 - Create configured shares (for e.g. romaing profiles)
 - Load configured GPO-Templates
 - Load configured GPO's
 - Install TLS-certificates for LDAP-access

I've started out from

 - https://galaxy.ansible.com/uspdev/sambadc

but then basically re-wrote the entire ansible script, partly with
some input from:

 - https://www.kania-online.de/wp-content/uploads/2020/10/samba-dc-10-22-20.tar

My use-case for this ansible-script is to run a small home-network where the
PDC is also the fileserver. This is not recommended by the Samba-Team, but for my
use-case this is good fit.
I do not have a RAID, but a simple PC with SSD for the Operating System and harddisk
for the data. The data from the harddrive is once per day mirrored to a second
installed harddrive. This second harddrive is configured to sleep and wakes only
for mirroring the data as backup.
In case the harddrive fails, I can easily swap the path in smb.conf
to the second harddrive, restart samba and contiue using the PDC with minor data loss.

My use of this ansible script therefore is a backup of my PDC, which I can re-deploy
if needed.

Supported systems
-----------------

This script is tested for the system I use, i.e. Ubuntu Server 22.04 LTS. I have also
tested it with Proxmox on a Virtual machine based on Debian. So although not tested in this
version, it shall work also on Debian based systems.

Tags
----

This role has the following tags defined:

 - dns_bind_dlz
 - gpo
 - cleanup
 - install
 - settings
 - limits
 - shares
 - check


Example Playbook
----------------

This example shall work out of the box on Ubuntu Server 22.04 LTS and probably other Debian
based systems.

    - hosts: all
      roles:
         - marioqxx.install_samba

Usage
-----


TODO: Write README.

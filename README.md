ansible-role-samba4-ad-member
=============================

Join Ubuntu as a member server to Active Directory

**Domain Admins have sudo rights**

Requirements
------------

- Ubuntu 16.04lts / 18.04lts AMD64
- Active Direcory (2008r2 and up)
- Ansible-role-ntp-server

Role Variables
--------------

See default/main.yml for detailed information.

Example Playbook
----------------

This is an example how to use the role:

    - hosts: ad-members
      become: true

      vars:
        # -- custom settings - ansible-role-samba4-ad-member --
        smb_workgroup: example
        smb_realm: EXAMPLE.LOCAL
        smb_dns_servers: 192.168.0.1 192.168.0.2
        smb_username: adm_ansible
        smb_password: '{{ ad_admin_pass }}'

      roles:
        - ansible-role-samba4-ad-member 


Source(s)
---------
Thanks goes to all the authors and participants from 
the sources below, so I could write this Anisble role.

- https://www.tecmint.com/join-ubuntu-to-active-directory-domain-member-samba-winbind/
- https://community.centrify.com/t5/Centrify-Express/Ad-group-with-space-in-its-name-not-working/td-p/17661
- https://wiki.samba.org/index.php/PAM_Offline_Authentication

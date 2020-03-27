Role Name
=========

This is a very basic role to help get a simple instance of the Folding@home
client onto a bunch of servers. We're using it at [Spruce^ki](https://spruce.ki)
to donate spare processing power of our staging infrastructure.

Please please please do not use this role in production, no matter how much you
want to put those powerful servers to good use! It's not guaranteed fit for
purpose - there are even speeling mistakes in the readme for crying out loud!

Requirements
------------

Currently only targets recent versions of CentOS/RHEL and Debian/Ubuntu. Pull
requests for other OSs would be welcomed!

Role Variables
--------------

The following defaults are set and are used in config.xml:

gpu: false
power: light
user: anonymous
state: present (use 'absent' to stop F@h and uninstall the RPM)

Dependencies
------------

N/A

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: peteroyle.folding-at-home, user: spruce^ki, state: present }

License
-------

Apache

Author Information
------------------

[Spruce^ki](https://spruce.ki) develops a full-featured, cloud-based
telecommunications platform used by many Australian-based telcos. Visit
[https://www.fyitelcoworks.com.au] to see it in action.

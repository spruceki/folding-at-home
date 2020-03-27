Role Name
=========

This is a very basic role to help get a simple instance of the Folding@home
client onto a bunch of servers. We're using it a Spruce^ki to donate spare
processing power of our staging infrastructure.

Please please please do not use this role in production, no matter how much you
want to put those powerful servers to good use! It's not guaranteed fit for
purpose - there are even speeling mistakes in the readme for crying out loud!

Requirements
------------

Currently only targets CentOS servers. Pull requests for other OSs would be
appreciated.

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

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - { role: folding-at-home, user: spruce^ki, state: present }

License
-------

Apache

Author Information
------------------

Spruce^ki develops a full-featured, cloud-based telecommunications platform used
by many Australian-based telcos. Visit https://www.fyitelcoworks.com.au to see
it in action.

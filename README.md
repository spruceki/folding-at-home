Role Name
=========

This is a very basic role to help get a simple instance of the Folding@home
client onto a bunch of servers. We're using it at [Spruce^ki](https://spruce.ki)
to donate spare processing power of our staging infrastructure.

Please please please do not use this role in production, no matter how much you
want to put those powerful servers to good use! It's not guaranteed fit for
purpose - there are even speeling mistakes in the readme for crying out loud!
Also it will probably send your monitoring/alerting into meltdown.

Requirements
------------

Currently only targets recent versions of CentOS/RHEL and Debian/Ubuntu. Pull
requests for other OSs would be welcomed!

Impact
------

Our servers are CPU only, and this role would require slight modification to
support GPUs. So we won't be breaking any records for points earned - my single
laptop is outstripping our entire staging environment by a factor of 10 wrt
points earned.

However, in terms of the number of WUs solved, the staging environment is ahead
of that laptop by a factor of 40. As I understand it there are certain types of
work that can't be done on GPUs, so throwing more CPUs into the mix is still
helpful.

Role Variables
--------------

The following defaults are set and are used in config.xml:

* gpu: false
* power: light (other options are 'medium' and 'full')
* user: ansible.spruce.ki (set to your desired username for stats reporting)
* team: 257758 (this is team "spruce.ki", feel free to use it or adjust as necessary. set to 0 for "no team")
* state: present (use 'absent' to stop and uninstall the F@h package)

Dependencies
------------

N/A

Example Playbook
----------------

This is the config we're using on our staging servers. So far under full power
we haven't noticed any impact on our productivity, but YMMV.

    - hosts: servers
      roles:
        - { role: peteroyle.folding_at_home, user: ansible.spruce.ki, team: 257758, state: present, power: full }

License
-------

Apache

Author Information
------------------

[Spruce^ki](https://spruce.ki) develops a full-featured, cloud-based
telecommunications platform used by many Australian-based telcos. Visit
[https://www.fyitelcoworks.com.au] to see it in action.

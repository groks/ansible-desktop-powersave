desktop-powersave
========

An [ansible role](https://galaxy.ansibleworks.com/list#/roles/222) to enable
power saving features on laptops with mostly Intel components.

- disable watchdogs which keep the laptop awake
- delay flushes to disk which let disk sleep longer
- disable Wake On Lan for the ethernet card
- enable power saving features of the:
  - PCI devices
  - SATA disks
- enable the power saving features of the Intel:
  - graphics chip
  - sound chip
  - wifi card

    ---
    - hosts: localhost

      roles:
        - groks.desktop-powersave

The role should run fine on machines without Intel components, it just won't
have as much effect.

Run `powertop` after a reboot to verify progress.

Requirements
------------

An installation of [Fedora](https://fedoraproject.org/get-fedora) on an Intel laptop.

Role Variables
--------------

Wait 15 seconds before flushing disk buffers:

    vars:
      - desktop_powersave_dirty_writeback_centisecs: 1500

Dependencies
------------

None.

License
-------

BSD

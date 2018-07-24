DB
=========

This role setups a sqlite DB complete with schema.

Requirements
------------
 SQLITE must be installed 


Role Variables
--------------

Not required

Dependencies
------------

Requies the SQLITE binaries and install direcotry /home/sqlite

Example Playbook
----------------
Role is called from AutomationLogic.yml

- name: prepare nginx and PHP installation
  hosts: all 
  gather_facts: False
  become: yes
  roles:
        -  nginx
        -  php
        -  db


License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

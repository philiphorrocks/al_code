PHP
=========

This role deploys the php packages and mycypt binary to 2 Ubuntu Web hosts. This is a standard packaged via an apt installation.

The following packages are install:

      - git
      - mcrypt
      - php5-cli
      - php5-curl
      - php5-fpm
      - php5-intl
      - php5-json
      - php5-mcrypt
      - php5-sqlite
      - sqlite3

Requirements
------------

No pre-reqs for this install. This is a standard apt install


Role Variables
--------------

There are no variables ae held locally in the role and include the following:


----------------

This role is triggered by calling the playbook AytomationLogic.yml. This playbook is automatically called via the Vagranfile provisioner 

- name: prepare nginx and PHP installation
  hosts: all 
  gather_facts: False
  become: yes
  roles:
        -  nginx
        -  php


License
-------

BSD


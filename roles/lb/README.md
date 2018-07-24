LB
=========

This role deploys the nginx LB package to 1 Ubuntu LB hosts. This is a standard packaged via an apt installation.

The following packages are install:

      - nginx 

Requirements
------------

No pre-reqs for this install. This is a standard apt install


Role Variables
--------------

There are no variables held locally in the role


----------------

This role is triggered by calling the playbook AytomationLogicLB.yml. This playbook is automatically called via the Vagranfile provisioner 

- name: setup LB and configuration
  hosts: all 
  gather_facts: False
  become: yes
  roles:
        - {role: nginx, sudo: yes, tags: ['install_nginx']  }
        - {role: lb, sudo: yes }

License
-------

BSD


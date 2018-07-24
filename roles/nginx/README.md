Nginx
=========

This role deploys the nginx packages to all 3 Ubuntu hosts. This is a standard packaged via an apt installation.

Requirements
------------

No pre-reqs for this install. This is a standard apt install


Role Variables
--------------

The vaibales ae held locally in the role and include the following:

# vars file for ngnix
epel_repo_url
epel_repo_gpg_key_url
epel_repofile_path
worker_processes
multi_accept
worker_connections 
access_log
error_log
server_tokens
sendfile
tcp_nodelay
tcp_nopush
keepalive_timeout
gzip

 

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


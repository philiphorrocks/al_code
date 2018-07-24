AL Test
=========

This playbook configures the following:

	- Install nginx packages and config files on 3 hosts
        - Configure nginx on 2 Web hosts as an application server
        - Configure nginx on 1 host as Loadbalacer
        - Configure PHP on 2 web hosts
        - Pull php helloworld application for GIT repo
        - Update sudo rules for vagrant user and admin group
        - Configure Load blancer to round robin between 2 web hosts 


Requirements
------------

This playbook requires the follwoing packages to be installed:

       - Ansible 2.x
       - Vagrant
       - Virtualbox


How to use this playbook
------------------------
    
To use this playbook, following the steps below:

Clone files form Git repository and run vagrant command below

       - git clone
       - vagrant up --provision 



License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

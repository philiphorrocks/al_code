AL Test
=========

This playbook configures the following:

	- Install nginx packages and config files on 3 hosts
        - Configure nginx on 2 Web hosts as an application server
        - Configure nginx on 1 host as Loadbalacer
        - Configure PHP application on 2 web hosts
        - Pull php helloworld application from GIT repo (https://github.com/philiphorrocks/al_test.git)
        - Update sudo rules for vagrant user and admin group
        - Configure Load blancer (http://192.168.56.103/al/helloworld.php)  round robin between 2 web hosts 
        - Install SQLite DB and schema (Used by PHP application to display helloworld message)
        - Test the all URLs for correct content

Requirements
-------------

This playbook requires the follwoing packages to be installed:

       - Ansible 2.x
       - Vagrant
       - Virtualbox


How to use this playbook
------------------------
    
To use this playbook, following the steps below:

Clone files form Git repository and run vagrant command below

       - git clone https://github.com/philiphorrocks/al_code.git
       - cd al_code
       - vagrant up --provision 
       - http://192.168.56.103/al/helloworld.php (This is the LB address for testing)

This will use the Vagrantfile to build 3 Ubuntu (puppetlabs/ubuntu-14.04-64-nocm) hosts (1 x LB and 2 x Web)

       - web1:http://192.168.56.101 
       - web2:http://192.168.56.102
       - lb1: http://192.168.56.103


Ansible will install nginx on all 3 hosts. 2 hosts will be configured with a nginx web server and the remaining host will be configured as a nginx load balancer. The 2 web hosts will also have PHP and SQLite installed. The PHP application will connect directly to the backed database which will provide the message string "helloworld". 


Testing:
--------

To test the application, hit the LB URL http://192.168.56.103/al/helloworld.php. You should see the server IP change as the LB round robins the requests to the backed web servers. You should also see the conenction the backend SQLite DB which will display the "helloworld" message.  

I test all web pages for content to validate and confirm they are running

- name: ensure web page is available 
  uri:
    url: http://localhost:80/al/helloworld.php
    return_content: yes
  register: page_test 

- name: ensure content is present on the page 
  assert:
    that:
      - "'Database message' in page_test.content"



License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

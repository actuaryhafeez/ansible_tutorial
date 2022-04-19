# ansible_tutorial

Welcome
This repository provides you with sample playbooks for all sorts of things.

The playbooks were tested to run agains ubuntu, debian, and centos systems.

The basic setup consists of an ansible user for each systems.

You need to do the following to allow key based ssh authentication.

    sudo su - ansible
    ssh-keygen 
    ssh-copy-id ansible@localhost
    ssh-copy-id ansible@ubuntu/ip
    ssh-copy-id ansible@debian/ip
   

Make sure you copy the key to the host itself too.

Python is needed for ansible to work so you should have at least a version 2.* on each system against which you work.

If you use a centos based machine perform these tasks before you do anything.

    yum update
    yum install python python-devel ansible openssl

Steps to perform on each host for key based authentication.

    adduser ansible
    passwd ansible

Use the visudo to add passwordless sudo to the user. Look for the line root and add the folowing below.

    visudo

ansible ALL=(ALL) NOPASSWD: ALL

In order to install ansible-cmdb to generate reports do the following.

    sudo su - 
    pip install --upgrage pip
    pip install ansible-cmdb

To generate the report from the facts do the following.

    ansible -m setup --tree facts/ all
    ansible-cmdb facts/ > overview.html

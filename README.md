Description

Here is an example of deploying Django project
based on MySQL, uWSGI, supervisor, nginx, Vagrant and Ansible
and according to the technical specifications:

1 Constants
Base system: Ubuntu 14.04.03 LTS
Django app: https://github.com/kirpit/django-sample-app
Django projectname: task1
Domain name: sample.example.com
Database:
name: django
user: mysql_user
pass: mysql_pass

2 Task details
use Virtualbox
you have to configure Django app with NGINX frontend, MySQL as database engine and uWSGI between Django and NGINX;
to start uWSGI use supervisor;
we need dedicated user for Django backend;
generate password for root user, keep it secret;
use Vagrant to provision VM on `vagrant up`;
use Ansible to provision Django app
combine Vagrant and Ansible, we want Vagrant to start Ansible.

How to run

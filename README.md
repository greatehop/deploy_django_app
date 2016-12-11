# deploy_django_app

## Description

Here is an example of deploying Django project with Vagrant and Ansible.
It is based on MySQL, uWSGI, supervisor, nginx - according to the technical specifications:

<pre>
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
- use Virtualbox
- you have to configure Django app with NGINX frontend, MySQL as database engine and uWSGI between Django and NGINX
- to start uWSGI use supervisor
- we need dedicated user for Django backend
- use Vagrant to provision VM on "vagrant up"
- use Ansible to provision Django app
- combine Vagrant and Ansible, we want Vagrant to start Ansible
</pre>

## How to run

Install software:

<pre>
$ sudo apt-get -y install python-pip git vagrant virtualbox virtualbox-dkms
</pre>

Update pip and ansible to the latest version:

<pre>
$ sudo apt-get -y remove ansible
$ sudo pip install --upgrade pip
$ sudo pip install --upgrade ansible
</pre>

Download repo and start provisioning:

<pre>
$ git clone https://github.com/greatehop/deploy_django_app && cd deploy_django_app
$ vagrant up
</pre>

Add fake dns:

<pre>
$ sudo sh -c "echo '\n192.168.55.55    sample.example.com' >> /etc/hosts"
</pre>

Open in browser:

http://sample.example.com

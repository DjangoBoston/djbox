# djbox

Django Box - A project to set up a boilerplate Django environemnt in a Vagrant box using ansible


## Overview

This is a sandbox/boilerplace project to demonstrate one way of setting up a Django app development environment in Vagrant using Ansible

This has been tested in the following environment:

* OS X 10.11.6
* Virtualbox 5.1.22
* Vagrant 1.9.5
* Ansible 2.2.2.0


## Development environment setup

* Install virtualbox (https://www.virtualbox.org/) - 
* Install Vagrant (https://www.vagrantup.com/)
* Open a command shell (go to the command line). The remaining commands will be run via the shell
* Install ansible. I recommend using a virtual env, but you can install ansible globally too. `pip install ansible`. If you use homebrew on OS X, you can run `brew install ansible`

* Run `vagrant plugin install vagrant-vbguest`. This automates installing Virtualbox guest additions which can address errors with getting synched folders working
* Navigate or create a project parent directory. This wil be the parent of the 'djbox' project space.
* Clone the djbox repo: `clone https://github.com/DjangoBoston/djbox.git`
* cd to the 'djbox' directory
* run `vagrant up`

This will setup your vagrant box and run the ansible provisioning scripts. Assuming there are no errors, you should be ready to try out the Django app. Go to the section 'Setup and run the app'

## Setup and run the app

* From the command line in your 'djbox' folder, run `vagrant ssh`. You should now be user `vagrant` in the VM.
* Run `sudodjsite` which is an alias for `sudo su djsite -s /bin/bash`. This will switch you to be the 'djsite' user

You should now be logged in as the 'djsite' user, in the user's home directory with the Django app's virtual environment running.

* `cd app/djsite`
* Run `./manage.py migrate` For this sandbox project, you should only need to run this once
* Run `runserver`, which is an alias for `./manage.py runserver 0.0.0.0:8000`. Note: It is important to set the host to `0.0.0.0` so that you can access the site from your host

From your host, open a browser to `localhost:8081` and you should see your Django app



## Closing

That's all for now. This is a sandbox project to demonstrate one way of getting your Django project set up in Vagrant

If you find bugs, run into issues, please submit a bug report here: https://github.com/DjangoBoston/djbox/issues

Thanks!

-John

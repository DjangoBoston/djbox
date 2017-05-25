# djbox

Django Box - A project to set up a boilerplate Django environemnt in a Vagrant box using ansible

# Setup

## Development environment

install virtualbox 

vagrant plugin install vagrant-vbguest

run `vagrant up`


vagrant ssh

you should now be the vagrant user

run `sudodjsite` which is an alias for `sudo su djsite -s /bin/bash`


run `cd`




## Production environments

TBD



# ---------------------------------------------------
# Notes to sort/organize

## Ansible primer

_Talk about what ansible is, what it does, how it works. Ref resources to learn more..._

Ansible is a configuration management and provisioning toolkit/platform. 

There are a number of popular CM/provioning tools. Ansibleis just one of them

It is written in Python and primarily uses YAML files for configuration. It is pretty flexible and you can do some simple tings without a steep learning curve. The thing with it is that to do any serious provisioning of scale, you are going to run into complexity whichever path you take.

What do I mean by this? There are very feature rich tools like chef, puppet ( TODO: have a slide with the CM tools, summary of how they work, and the languages in which they are implemented)



## Ansible architecture for the Django sandbox

The `VagrantFile` runs the `deploy/vagrant.yml` 

`deploy/vagrant`  has the following

```
- include: add_python2.yml
- include: djbox.yml
- include: vagrant_env.yml
```

the `add_python2.yml` playbook adds Python2 to the Ubuntu 16.04 environment, which does not have it by default.

The djbox.yml playbook sets up the virtual machine to run the demonstration Django app (which currently only runs in development mode)

The vagrant_env.yml playbook sets up the vagrant specific environment (runs the vagrant_env role)

This playbook (and corresponding role) is not required. It is for convenience.

### Vagrant Env playbook and role

creates dot files for the vagrant user. 



## Running ansible in the Vagrant environment





## Setting up and running Django

shell in as the djbox user
run runserver (alias for manage...)


# ---------------------------------------------------
# TODO

set up env var file for running

* pip as the djsite user

Need to fix where the djsite user files are going. Right now they are being installed in /home/djsite/app


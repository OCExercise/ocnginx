# Overview

## Motivation

## 

# Installation

## Prerequisites

We'll be using

* [Virtualbox 5.x](https://www.virtualbox.org/) as the default target, 
* [Vagrant 1.7.x](https://www.vagrantup.com) as the instance configurator and runner, and 
* [Ansible 1.6.x](https://github.com/ansible/ansible) as the system provisioner. 

### OS X

If you haven't, install [Homebrew](http://brew.sh/) and [Cask](http://caskroom.io/).   

```
$ brew install ansible
$ brew cask install virtualbox vagrant vagrant-manager
```

### RHEL/Fedora/CentOS

Coming soon.

### Debian/Ubuntu

Coming soon.

### Windows

Coming soon.

## Installation

```
$ git clone git@github.com:OCExercise/ocnginx.git
$ pushd ocnginx
$ ansible-galaxy install -r requirements.txt
```

# Execution and Exploration

```
$ vagrant up                    # Deploys a bare-bones Vagrant Box to
                                # VirtualBox (by default), sets up 
                                # SSH access and runs provisions via ansible
...
$ vagrant ssh-config >> ~/.ssh/config       # Easy access host for SSH

$ ssh -q ocnginx exit      # Test SSH connection to instance
$ echo $?
0

$ curl -I -X GET "http://192.168.33.34"    # Test nginx
$ curl -I -X GET "http://192.168.33.34:8000"    
```

# TODO

* Modify for proper operation on vanilla ubuntu/trusty64 and centos6 Vagrant boxes
* Idempotency for virtualhost configuration on error.

# Special Thanks

* [Jeff Gearling](http://jeffgeerling.com/): Making use of his [Vagrant box](https://atlas.hashicorp.com/geerlingguy/boxes/centos6) and two of his ansible roles for this task ([firewall](https://github.com/geerlingguy/ansible-role-firewall) and [nginx](https://github.com/geerlingguy/ansible-role-nginx)).
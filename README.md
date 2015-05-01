
# Description

This repo serves as a starting point to manage a general development environment for creating ruby applications.

# Services

The current version installs the following services on the VM:
* PostgreSQL
* Mongodb
* Redis
* RabbitMQ

# Prerequisites

* Install vagrant : https://www.vagrantup.com/downloads.html

## Install vagrant plugins
    vagrant plugin install vagrant-vbguest
    vagrant plugin install vagrant-librarian-chef-nochef

# Startup

    vagrant up
    vagrant ssh

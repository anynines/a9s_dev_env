# Description

This repo serves as a starting point to manage a general development environment for creating ruby and go applications. It provides service installations to be accessed by your applications.

# Services

The current version installs the following services on the VM:
* PostgreSQL
* Mongodb
* Redis
* RabbitMQ

All services can be accessed from the host system using their default ports and the host 127.0.0.1. For a list of forwarded ports please refer to the [Vagrantfile](Vagrantfile).

# Prerequisites

* [Install Virtualbox](https://www.virtualbox.org/wiki/Downloads)
* or [install VmWare](http://www.vmware.com/de/products/player)
* [Install Vagrant](https://www.vagrantup.com/downloads.html)


## Install vagrant plugins

    vagrant plugin install vagrant-vbguest
    vagrant plugin install vagrant-librarian-chef-nochef

# Startup

    # clone the repo
    git clone https://github.com/anynines/a9s_dev_env.git

    # enter the directory
    cd a9s_dev_env

    # start the vagrant machine
    vagrant up

    # ssh into the machine when the provisioning process has finished
    vagrant ssh

# Reprovisioning

When making changes to the Cheffile and Vagrantfile please reprovision the VM using the following commands:

    vagrant up
    vagrant provision

# Shared folders

The workspace folder is mounted to the VM under /vagrant/workspace.
Put your files (sources, ...) in this folder to be able to access the files from your guest and host systems.

# Default Service Authentication

* PostgreSQL: User: postgres ; password: test123!
* MongoDB: auth disabled -> all connections accepted
* Redis: auth disabled -> all connections accepted
* RabbitMQ: User: guest ; password: guest

# Troubleshooting

## Errors on reprovisioning

Error message: "Shared folders that chef requires are missing ...."

    rm .vagrant/machines/default/virtualbox/synced_folders
    vagrant reload --provision

## Windows Command log_filename

Please execute the commands above in a command line instance with administrator rights.

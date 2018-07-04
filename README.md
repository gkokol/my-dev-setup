# my-dev-server

Ansible and serverspec for my ubuntu server in vbox
Should possibly be extended to other OS's later

You should be able to run this from OS X.
Requires or has been tested with:
	* Vagrant 2.1.2
	* ansible 2.4.3.0 
	* virtualbox 5.2.1


# Vagrantfile

The initial Vagrantfile has been taken via:
	`vagrant init ubuntu/xenial64`

And then modified to set up users, mount shared folders, install necessary
packages.

When making changes to Vagrantfile, validate before applying them:
	`vagrant validate`
	`vagrant reload --provision`

## Shared folders
	update/alter config.vm.synced_folder in Vagrantfile

# Ansible

If changes are made, then reprovision
	`vagrant provision`

## Roles

	- vmsetup:
		Contains the packages that need to be installed
	- roles:
		Contains user info


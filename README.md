# my-dev-server

Ansible and serverspec for my ubuntu server in vbox for OSX.
Should possibly be extended to other OS's later

You should be able to run this from OS X.
Requires or has been tested with:

	* Vagrant 2.1.2
	* ansible 2.4.3.0
	* virtualbox 5.2.1


# Vagrantfile

The initial Vagrantfile has been taken via:
	
	vagrant init ubuntu/xenial64

And then slightly modified to mount shared folders, provision via ansible.

Use via:
	
	vagrant up - to start your vm
	vagrant halt` - to halt
	vagrant provision - to apply ansible changes if needed

When making changes to Vagrantfile, validate before applying them:
	
	vagrant validate
	vagrant reload --provision

## Shared folders
To add update shared folders use:
    
	config.vm.synced_folder
in Vagrantfile

# Ansible

If changes are made, then reprovision

	vagrant provision

## Roles

Ansible has been split into:
	
	- vmsetup:
		Contains the packages that need to be installed
	- roles:
		Contains user info

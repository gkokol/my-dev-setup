# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "vbubuntu"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Share the code Folder
  config.vm.synced_folder ENV['HOME'] + "/code", "/code"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "local-ubuntu-dev"
    vb.cpus = 4
    vb.memory = "4096"
    vb.customize ["modifyvm", :id, "--cpuexecutioncap", "100"]
    vb.customize ["modifyvm", :id, "--paravirtprovider", "hyperv"]
    # vb.customize ["modifyvm", :id, "--nic2", "hostonly", "--hostonlyadapter2", "vboxnet0"]
  end

  # Provision via ansible
  config.vm.provision "ansible" do |a|
    a.playbook = "vbox-vm.yml"
    #a.verbose = 'vvvv'
  end

end

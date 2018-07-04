# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "vbubuntu"

  # Create a private network, which allows host-only access to the machine
  config.vm.network "private_network", type: "dhcp"

  # Share the code Folder
  config.vm.synced_folder ENV['HOME'] + "/code", "/code"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "local-ubuntu-dev"
    vb.cpus = 4
    vb.memory = "4096"
    vb.customize ["modifyvm", :id, "--cpuexecutioncap", "100"]
    vb.customize ["modifyvm", :id, "--paravirtprovider", "hyperv"]
  end

  # Provision via ansible
  config.vm.provision "ansible" do |a|
    a.playbook = "vbox-vm.yml"
    #a.verbose = 'vvvv'
  end

end

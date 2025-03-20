# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Specify the Ubuntu 24.04 base box
  config.vm.box = "bento/ubuntu-24.04"

  # Set up the virtual machine
  config.vm.hostname = "ubuntu-vm"
  config.vm.network "private_network", type: "dhcp"

  # Allocate resources
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
  end

  # Provisioning
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt update && sudo apt upgrade -y
    sudo apt install -y build-essential curl git
  SHELL
end

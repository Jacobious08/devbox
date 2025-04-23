# -*- mode: ruby -*# -*- mode: ruby -*-
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
    sudo apt install -y curl wget vim
    curl -sfL https://get.k3s.io | sh -
    mkdir -p ~/.kube
    sudo cp /etc/rancher/k3s/k3s.yaml ~/.kube/config
    sudo chown $(id -u):$(id -g) ~/.kube/config
    export KUBECONFIG=~/.kube/config
  SHELL
end

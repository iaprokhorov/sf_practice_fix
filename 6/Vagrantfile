# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "PythonVM"
    vb.memory = "2048"
    vb.cpus = 1
  end

  config.vm.hostname = "python"
  config.vm.define "python3"
  config.vm.synced_folder "./code", "/home/vagrant/code",
    owner: "vagrant", group: "vagrant"

  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "private_network", ip: "192.168.100.20"
  config.vm.provision "shell", path: "provision.sh"
end

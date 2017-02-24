# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "hashicorp/precise32"

  config.vm.hostname = "ldap.example.com"

  #config.vm.network "private_network", ip: "192.168.33.253"
  config.vm.network "forwarded_port", guest: 80, host: 1234
  config.vm.network "forwarded_port", guest: 389, host: 3890

  config.vm.provider "virtualbox" do |vb|
    vb.linked_clone = true
    vb.memory = "1024"
  end

  config.vm.provision "shell", path: "provision.sh"
end

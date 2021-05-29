# -*- mode: ruby -*-
# vi: set ft=ruby:

Vagrant.configure("2") do |config|
  config.vm.define "ansible" do |ansible|
    ansible.vm.box = "centos/8"
    ansible.vm.hostname = "ansible"
    ansible.vm.network "private_network", ip: "10.67.17.10", virtualbox_intnet: true

    ansible.vm.provider "virtualbox" do |vb|
      vb.name = "ansible"
      vb.cpus = 1
      vb.memory = 512
    end
    ansible.vm.provision "shell", path: "ansible.sh"
  end

  config.vm.define "target" do |vm2|
    vm2.vm.box = "centos/8"
    vm2.vm.hostname = "centos-vm"
    vm2.vm.network "private_network", ip: "10.67.17.11", virtualbox_intnet: true

    vm2.vm.provider "virtualbox" do |vb|
      vb.name = "centos-vm"
      vb.cpus = 1
      vb.memory = 512
    end
    vm2.vm.provision "shell", path: "target.sh"
  end

end

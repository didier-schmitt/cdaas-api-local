# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "box-cutter/centos72"
  config.vm.hostname = "cdaas.localdomain"
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.name = "[Vagrant] Local CDaaS API"
    vb.memory = "1024"
    vb.cpus = 1
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.install = true
    ansible.playbook = "playbook.yml"
    ansible.provisioning_path = "/vagrant/ansible"
  end
end

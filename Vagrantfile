# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define "ambari" do |ambari|
    ambari.vm.box = "hdp_vm"
    ambari.vm.hostname = "ambari"
    ambari.vm.network "public_network", ip: "192.168.1.110"
    ambari.vm.network "forwarded_port", guest: 8080, host: 8081
    ambari.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
  end

  config.vm.define "hdpa" do |hdpa|
    hdpa.vm.box = "hdp_vm"
    hdpa.vm.hostname = "hdpa"
    hdpa.vm.network "public_network", ip: "192.168.1.111"
    hdpa.vm.network "forwarded_port", guest: 8080, host: 8082

    hdpa.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
  end

  # Ansible provisioner.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ambari.yml"
    ansible.inventory_path = "inventory"
    ansible.sudo = true
  end

end



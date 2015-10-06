# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define "ambari" do |ambari|
    ambari.vm.box = "hdp_vm"
    ambari.vm.hostname = "ambari"
    ambari.vm.network "public_network", ip: "192.168.1.110", bridge: "eth2"
    ambari.vm.network "forwarded_port", guest: 8080, host: 8081 
    ambari.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end

  config.vm.define "hdpa" do |hdpa|
    hdpa.vm.box = "hdp_vm"
    hdpa.vm.hostname = "hdpa"
    hdpa.vm.network "public_network", ip: "192.168.1.111", bridge: "eth2"

    hdpa.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end
  config.vm.define "hdpb" do |hdpb|
    hdpb.vm.box = "hdp_vm"
    hdpb.vm.hostname = "hdpb"
    hdpb.vm.network "public_network", ip: "192.168.1.112", bridge: "eth2"

    hdpb.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end
  config.vm.define "hdpc" do |hdpc|
    hdpc.vm.box = "hdp_vm"
    hdpc.vm.hostname = "hdpc"
    hdpc.vm.network "public_network", ip: "192.168.1.113", bridge: "eth2"

    hdpc.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end
  config.vm.define "hdpd" do |hdpd|
    hdpd.vm.box = "hdp_vm"
    hdpd.vm.hostname = "hdpd"
    hdpd.vm.network "public_network", ip: "192.168.1.114", bridge: "eth2"

    hdpd.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end
  config.vm.define "hdpe" do |hdpe|
    hdpe.vm.box = "hdp_vm"
    hdpe.vm.hostname = "hdpe"
    hdpe.vm.network "public_network", ip: "192.168.1.115", bridge: "eth2"

    hdpe.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end
  config.vm.define "hdpf" do |hdpf|
    hdpf.vm.box = "hdp_vm"
    hdpf.vm.hostname = "hdpf"
    hdpf.vm.network "public_network", ip: "192.168.1.116", bridge: "eth2"

    hdpf.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
  end

  # Ansible provisioner.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ambari.yml"
    ansible.inventory_path = "inventory"
    ansible.sudo = true
  end

end



# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define "web" do |web|
    web.vm.box = "hdp_vm"
    web.vm.hostname = "ambari"
    web.vm.network "public_network", ip: "192.168.1.110"
    web.vm.network "forwarded_port", guest: 8080, host: 8081
    web.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "hdp_vm"
    db.vm.hostname = "hdpa"
    db.vm.network "public_network", ip: "192.168.1.111"
    db.vm.network "forwarded_port", guest: 8080, host: 8082

    db.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
  end
end


# -*- mode: ruby -*-
# vi: set ft=ruby :

#boxes = [
#         {
#           :name => "hdpa",
#           :eth1 => "192.168.1.111",
#           :mem => "10240",
#           :cpu => "2"
#         },
#         {
#           :name => "hdpb",
#           :eth1 => "192.168.1.112",
#           :mem => "10240",
#           :cpu => "2"
#         },
#         {
#           :name => "hdpc",
#           :eth1 => "192.168.1.113",
#           :mem => "10240",
#           :cpu => "2"
#         },
#         {
#           :name => "hdpd",
#           :eth1 => "192.168.1.114",
#           :mem => "10240",
#           :cpu => "2"
#         },
#         {
#           :name => "hdpe",
#           :eth1 => "192.168.1.115",
#           :mem => "10240",
#           :cpu => "2"
#         },
#         {
#           :name => "hdpf",
#           :eth1 => "192.168.1.116",
#           :mem => "10240",
#           :cpu => "2"
#         },
#        ]

require_relative './vagrant/key_authorization'

Vagrant.configure(2) do |config|

  authorize_key_for_root config, '~/.ssh/id_dsa.pub', '~/.ssh/id_rsa.pub'
  {
    'ambari'    => '192.168.1.110',
    'hdpa'   => '192.168.1.111',
    'hdpb' => '192.168.1.112',
    'hdpc' => '192.168.1.113',
    'hdpd' => '192.168.1.114',
    'hdpe' => '192.168.1.115',
    'hdpf' => '192.168.1.116',
  }.each do |short_name, ip|
    config.vm.define short_name do |host|
      host.vm.network 'public_network', ip: ip, bridge: "eth2"
      host.vm.hostname = "#{short_name}.dev"

      host.vm.provider "virtualbox" do |vb|
        vb.memory = "8096"
        vb.cpus = "2"
      end
    end
  end

#  boxes.each do |opts|
#    config.vm.define opts[:name] do |v|
#      v.vm.box = "hdp_vm"
#      v.vm.hostname =  opts[:name]
#      v.vm.network "public_network", ip: opts[:eth1], bridge: "eth2"
#      
#      v.vm.provider "virtualbox" do |vb|
#        vb.memory = opts[:mem]
#        vb.cpus = opts[:cpu]
#      end
#    end
#  end

#  config.vm.define "ambari" do |ambari|
#    ambari.vm.box = "hdp_vm"
#    ambari.vm.hostname = "ambari"
#    ambari.vm.network "public_network", ip: "192.168.1.110", bridge: "eth2"
#    ambari.vm.network "forwarded_port", guest: 8080, host: 8081 
#    ambari.vm.provider "virtualbox" do |vb|
#      vb.memory = "8096"
#      vb.cpus = 2
#    end
    # Ansible provisioner.
#    config.vm.provision "ansible" do |ansible|
#      ansible.playbook = "ambari.yml"
#      ansible.inventory_path = "inventory"
#      ansible.sudo = true
#      ansible.raw_ssh_args = ['-o IdentitiesOnly=yes']
#      #ansible.limit = "all"
#      ansible.verbose = "vvv"
#    end

#  end



end



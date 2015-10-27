# -*- mode: ruby -*-
# vi: set ft=ruby :

require_relative './vagrant/key_authorization'

Vagrant.configure(2) do |config|

  config.vm.box = 'hdp_vm'
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

      #host.vm.provider "virtualbox" do |vb|
      #  vb.memory = "8096"
      #  vb.cpus = "2"
      #end
    end
  end

end



# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.

  config.ssh.insert_key = false
  config.vm.define "hostinfo-server" do |server|
    server.vm.box = "centos/7"
    server.vm.hostname = "hostinfo-server"
    server.vm.network "forwarded_port", guest: 80, host:  8088
    server.vm.network "private_network", ip: "192.168.51.2"
#    server.vm.provider "virtualbox" do |vb|
#      vb.memory = "4096"
#    end
#    server.vm.provision "ansible" do |ansible|
#      ansible.playbook = "playbooks/system_provision.yml"
#      ansible.limit = "go-server"
#    end
    server.ssh.insert_key = false
  end

  config.vm.define "host01" do |agent|
    agent.vm.box = "centos/7"
    agent.vm.hostname = "host01"
    agent.vm.network "private_network", ip: "192.168.51.3"
#    agent.vm.provider "virtualbox" do |vb|
#      vb.memory = "1024"
#    end
#    agent.vm.provision "ansible" do |ansible|
#      ansible.playbook = "playbooks/system_provision.yml"
#      ansible.limit = "go-agent"
#    end
    agent.ssh.insert_key = false
  end
end

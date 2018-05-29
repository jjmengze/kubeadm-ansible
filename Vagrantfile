# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "master" do |config|
  config.vm.box = "bento/ubuntu-16.04"
  config.vm.hostname = 'master'
  config.vm.network "private_network", ip: "192.168.0.10",auto_config: true
  config.vm.provider :virtualbox do |v|
      v.gui = false
      v.customize ["modifyvm", :id, "--cpuexecutioncap", 30]
      # enable this when you want to have more memory
      v.customize ["modifyvm", :id, "--memory", 1500]
      v.customize ['modifyvm', :id, '--nicpromisc1', 'allow-all']
  end
#  config.vm.synced_folder "./", "/opt"
  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    set -e -x -u
    sudo sed -i 's/us.archive.ubuntu.com/tw.archive.ubuntu.com/g' /etc/apt/sources.list
    sudo apt-get update && sudo apt-get install software-properties-common
    sudo apt-add-repository ppa:ansible/ansible -y
    sudo apt-get update
    sudo apt-get install ansible -y
  SHELL
  end

  config.vm.define "node1" do |config|
  config.vm.box = "bento/ubuntu-16.04"
  config.vm.hostname = 'node1'
  config.vm.network "private_network", ip: "192.168.0.11",auto_config: true
  config.vm.provider :virtualbox do |v|
      v.gui = false
      v.customize ["modifyvm", :id, "--cpuexecutioncap", 30]
      # enable this when you want to have more memory
      v.customize ["modifyvm", :id, "--memory", 1500]
      v.customize ['modifyvm', :id, '--nicpromisc1', 'allow-all']
  end
  end
end


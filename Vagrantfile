# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.4"
  config.ssh.insert_key = false

  config.vm.define "awx-0001" do |awx|
    awx.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
    end
    awx.vm.hostname = "awx-0001"
    awx.vm.network "private_network", ip: "192.168.1.1"
    awx.vm.network "forwarded_port", guest: 80, host: 10080

    awx.vm.provision :ansible do |ansible|
      ansible.playbook = "awx.yml"
    end
  end

  config.vm.define "server-0001" do |s1|
    s1.vm.provider "virtualbox" do |v|
      v.memory = 512
      v.cpus = 1
    end
    s1.vm.hostname = "server-0001"
    s1.vm.network "private_network", ip: "192.168.1.2"
    s1.vm.network "forwarded_port", guest: 80, host: 11080
  end
end

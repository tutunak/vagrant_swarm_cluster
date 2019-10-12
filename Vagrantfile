# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|

  config.vm.define "master" do |master|
    master.vm.box = "centos/7"
    master.vm.network "private_network", ip: "192.168.1.10"
    master.vm.provision "shell",
      inline: "yum install git -y"
    master.vm.provision 'ansible', run: 'always', type: :ansible_local do |ansible|
      ansible.galaxy_role_file = 'requirements.yml'
      ansible.playbook = 'playbook.yml'
    end
  end

  config.vm.define "node1" do |node1|
    node1.vm.box = "centos/7"
    node1.vm.network "private_network", ip: "192.168.1.11"
    node1.vm.provision "shell",
      inline: "yum install git -y"
    node1.vm.provision 'ansible', run: 'always', type: :ansible_local do |ansible|
      ansible.galaxy_role_file = 'requirements.yml'
      ansible.playbook = 'playbook.yml'
    end
  end

  config.vm.define "node2" do |node2|
    node2.vm.box = "centos/7"
    node2.vm.network "private_network", ip: "192.168.1.12"
    node2.vm.provision "shell",
      inline: "yum install git -y"
    node2.vm.provision 'ansible', run: 'always', type: :ansible_local do |ansible|
      ansible.galaxy_role_file = 'requirements.yml'
      ansible.playbook = 'playbook.yml'
    end
  end
end

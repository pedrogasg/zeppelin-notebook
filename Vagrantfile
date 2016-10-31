# -*- mode: ruby -*-
# vi: set ft-ruby :

Vagrant.configure(2) do |config|
  config.vm.provision "ansible" do |ansible|
    ansible.groups = {
     "mesos" => ["mesos-a-01"]
    }
    ansible.extra_vars = { ansible_ssh_user: 'vagrant' }
    ansible.playbook = "ansible/playbook.yml"
  end
  config.vm.define "mesos-a-01" do |mesos|
    mesos.vm.hostname = "mesos-a-01"
    mesos.vm.box = "bento/centos-7.1"
    mesos.vm.synced_folder "./sync/mesos-a-01/", "/sync"
    mesos.vm.provider "virtualbox" do |vm|
      vm.name = "mesos-a-01"
    end
    mesos.vm.network "private_network", ip:"192.168.10.60"
  end
end

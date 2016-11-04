# -*- mode: ruby -*-
# vi: set ft-ruby :

Vagrant.configure(2) do |config|
  config.vm.provision "ansible", run: "always" do |ansible|
    ansible.groups = {
     "mesos" => ["mesos-master-01","mesos-slave-01","mesos-slave-02","mesos-slave-03","mesos-slave-04"],
     "mesos-master" => ["mesos-master-01"],
     "mesos-slave" => ["mesos-slave-01","mesos-slave-02","mesos-slave-03","mesos-slave-04"]
    }
    ansible.extra_vars = { ansible_ssh_user: 'vagrant' }
    ansible.playbook = "ansible/playbook.yml"
  end
  config.vm.define "mesos-master-01" do |mesos|
    mesos.vm.hostname = "mesos-master-01"
    mesos.vm.box = "bento/centos-7.1"
    mesos.vm.synced_folder "./sync/mesos-master-01/", "/sync"
    mesos.vm.provider "virtualbox" do |vm|
      vm.name = "mesos-master-01"
      vm.cpus = 2
      vm.memory = 1024
    end
    mesos.vm.network "private_network", ip:"192.168.56.60"
  end
  config.vm.define "mesos-slave-01" do |mesos|
    mesos.vm.hostname = "mesos-slave-01"
    mesos.vm.box = "bento/centos-7.1"
    mesos.vm.synced_folder "./sync/mesos-slave-01/", "/sync"
    mesos.vm.provider "virtualbox" do |vm|
      vm.name = "mesos-slave-01"
      vm.cpus = 2
      vm.memory = 1024
    end
    mesos.vm.network "private_network", ip:"192.168.56.61"
  end
  config.vm.define "mesos-slave-02" do |mesos|
    mesos.vm.hostname = "mesos-slave-02"
    mesos.vm.box = "bento/centos-7.1"
    mesos.vm.synced_folder "./sync/mesos-slave-02/", "/sync"
    mesos.vm.provider "virtualbox" do |vm|
      vm.name = "mesos-slave-02"
      vm.cpus = 2
      vm.memory = 1024
    end
    mesos.vm.network "private_network", ip:"192.168.56.62"
  end
  config.vm.define "mesos-slave-03" do |mesos|
    mesos.vm.hostname = "mesos-slave-03"
    mesos.vm.box = "bento/centos-7.1"
    mesos.vm.synced_folder "./sync/mesos-slave-03/", "/sync"
    mesos.vm.provider "virtualbox" do |vm|
      vm.name = "mesos-slave-03"
      vm.cpus = 2
      vm.memory = 1024
    end
    mesos.vm.network "private_network", ip:"192.168.56.63"
  end
  config.vm.define "mesos-slave-04" do |mesos|
    mesos.vm.hostname = "mesos-slave-04"
    mesos.vm.box = "bento/centos-7.1"
    mesos.vm.synced_folder "./sync/mesos-slave-04/", "/sync"
    mesos.vm.provider "virtualbox" do |vm|
      vm.name = "mesos-slave-04"
      vm.cpus = 2
      vm.memory = 3072
    end
    mesos.vm.network "private_network", ip:"192.168.56.64"
  end
end

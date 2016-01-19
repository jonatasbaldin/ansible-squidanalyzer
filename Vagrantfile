# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define "ubuntu" do |ubuntu|
      ubuntu.vm.box = "ubuntu/trusty64"
      ubuntu.vm.hostname = "ubuntu"
      ubuntu.vm.network "private_network", ip: "192.168.53.10"
  end
 
  config.vm.define "centos" do |centos|
      centos.vm.box = "centos/7"
      centos.vm.hostname = "centos"
      centos.vm.network "private_network", ip: "192.168.53.11"
  end
  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "tests/test.yml"
    ansible.groups = {
      "centos" => ["centos"],
      "ubuntu" => ["ubuntu"],
    }
  end

end

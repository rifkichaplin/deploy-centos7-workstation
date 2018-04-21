# -*- mode: ruby -*-
# vi: set ft=ruby :
#

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "dockerhost"
  config.vm.network :forwarded_port, guest: 22, host: 2223, id: 'ssh'
  config.vm.network :forwarded_port, guest: 80, host: 3000 #grafana
  config.vm.network :forwarded_port, guest: 8081, host: 8081 #kibana
  config.ssh.port = 2223
  config.ssh.insert_key = false
  config.vm.network :private_network, ip: "192.168.1.10"
  config.ssh.forward_agent = true
   
  config.vm.provision "shell", inline: "unlink /usr/bin/python; ln /usr/bin/python3 /usr/bin/python"

#Add memory on vagrant
config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.name = "16.04-web01"
    vb.memory = "3048"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.host_key_checking = false
    ansible.playbook = "provision_vagrant.yml"
    ansible.limit = 'all'
    ansible.verbose = 'vvv'
    ansible.raw_ssh_args = ['-o ForwardAgent=yes']
  end

end

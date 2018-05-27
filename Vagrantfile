# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network :public_network
  config.vm.synced_folder './samba', '/usr/local/samba'
  config.vm.provider 'virtualbox' do |vb|
    vb.memory = 2048
    vb.cpus = 2
  end

  config.vm.provision 'shell', path: './provision/init.sh'
  config.vm.provision 'ansible' do |ansible|
    ansible.playbook = './provision/main.yml'
  end
end

# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "http://localhost/package.box"
  config.vm.synced_folder "./wordpress", "/wordpress/wp-content"

  config.vm.network "forwarded_port", guest: 80, host: 15080
  config.vm.network "forwarded_port", guest: 15022, host: 15022
  config.vm.network "forwarded_port", guest: 3306, host: 18306
  config.vm.network "forwarded_port", guest: 22, host: 2200

  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 1
  end

  config.ssh.port = 15022
  config.ssh.username = "web"
end

# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
  config.vm.box      = 'ubuntu/trusty64'
  config.vm.hostname = 'php56-dev'

  config.vm.network :forwarded_port, guest: 80, host: 8001
  config.vm.network :forwarded_port, guest: 3000, host: 3001
  config.vm.network :forwarded_port, guest: 8080, host: 8081
  config.vm.network :forwarded_port, guest: 9090, host: 9091
  config.vm.network :forwarded_port, guest: 10000, host: 10001
  config.vm.network "forwarded_port", guest: 3306, host: 3307

  config.vm.provision :shell, path: 'bootstrap.sh', keep_color: true

  config.vm.synced_folder "app", "/var/www"

  config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network "public_network"

  # config.vm.provider "virtualbox" do |vb|
  #   vb.gui = true
  #   vb.memory = "1024"
  # end
end

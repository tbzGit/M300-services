# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.synced_folder ".", "/var/www/html"

  config.disksize.size = "30GB"

  config.vm.provider "virtualbox" do |vb|

    vb.memory = "2048"

  end

  config.vm.provision "shell", inline: <<-SHELL
    ufw allow 80/tcp
    ufw allow from 127.0.0.1 to any port 22

    apt-get update

    apt-get -y install apache2
    ufw enable
  SHELL

end

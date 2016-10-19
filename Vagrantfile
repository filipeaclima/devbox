# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
  # The name of the Vagrant box to use
  config.vm.box = "facl/devbox"
  
  # The SSH password to use on first connection if you haven't configured SSH keys
  config.ssh.password = "vagrant"

  # The guest ports that are forwared on the host
  config.vm.network "forwarded_port", guest: 80, host: 8000
  config.vm.network "forwarded_port", guest: 3306, host: 3306
  config.vm.network "forwarded_port", guest: 6379, host: 6379
  config.vm.network "forwarded_port", guest: 8081, host: 8081

  # Create a new private network on the guest
  config.vm.network "private_network", ip: "192.168.56.2"

  config.vm.provider "virtualbox" do |vb|
    # The name of the virtual machine on Virtualbox
    vb.name = "friendly-name"
	# The amount of memory to allocate to the guest
	vb.memory = "2048"
  end

  # None of the scripts validate if its arguments are actually inputed by the user, so please use it as itendend.
  config.vm.provision "shell", inline: <<-SHELL
	# Script: new-nginx-server.sh
	# Description: Creates a new "virtual host" for nginx
	# Arguments:
	#   $1 (required): the server name of the "virtual host"
	#   $2 (required): the path for the document root
	#   $3 (optional): the listening port. Defaults to '80'
    sh /home/vagrant/scripts/new-nginx-server.sh my.app.local /vagrant
	# Script: new-database.sh
	# Description: Creates a new MariaDB database
	# Arguments:
	#   $1 (required): the name of the database
	#   $2 (optional): the charset of the database. Defaults to 'utf8'
	#   $3 (optional): the collation of the database. Defaults to 'utf8_general_ci'
	#   $4 (optional): the username to access MariaDB. Defaults to 'vagrant'
	#   $5 (optional): the password to access MariaDB. Defaults to 'vagrant'
	# If you don't need to specify agruments $2 and $3, but need to specify $4 or $5, please specify them all. No user input validations are made on the scripts!! 
	sh /home/vagrant/scripts/new-database.sh my_db
	# Script: new-host-entry.sh
	# Description: Creates a new entry on /etc/hosts
	# Arguments:
	#   $1 (required): the IP address of the entry
	#   $2 (required): the hostname that matches the IP address
	sh /home/vagrant/scripts/new-host-entry.sh 192.168.1.1 MY-MACHINE
  SHELL
end

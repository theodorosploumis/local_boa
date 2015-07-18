# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "Debian Wheezy 7.6 amd64 (Minimal + VirtualBox Guest Additions 4.3.16, 2014.09.28)"
  # BOA needs a vanilla box.
  # We got this from http://www.vagrantbox.es. Other boxes may work fine also.
  config.vm.box_url = "https://github.com/jose-lpa/packer-debian_7.6.0/releases/download/1.0/packer_virtualbox-iso_virtualbox.box"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  config.vm.box_check_update = false
  config.vbguest.auto_update = false

  # Set guest OS
  config.vm.guest = :debian

  # IMPORTANT! Enable login as root after running the BOA installer.
  # Because BOA will remove vagrant user fro the system!
  #config.ssh.username = "root"
  #config.ssh.password = 'vagrant'

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 3306, host: 3306

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # Example of local ip: 192.168.44.42
  config.vm.network "private_network", ip: "192.168.44.42"
  # plugin https://github.com/cogitatio/vagrant-hostsupdater
  config.hostsupdater.aliases = [
    # aegir installer will create these entries on host machine
    'aegir.local',
    'sub.aegir.local',
    'o1.sub.aegir.local',
    'chive.aegir.local',
    # Any sites that may be installed via aegir. Eg.
    #'dev.example.com',
  ]

  # Provider-specific configuration so you can fine-tune various backing providers for Vagrant.
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

end

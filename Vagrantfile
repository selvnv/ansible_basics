# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.

  # Конфигурация для запуска ВМ на debian
  # CLI: vagrant up debian
  config.vm.define "debian" do |debian|
    debian.vm.box = "generic/debian12"
    debian.vm.box_version = "4.3.12"
    debian.vm.hostname = "debianvm"
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    debian.vm.network "private_network", ip: "192.168.33.10"
    debian.vm.synced_folder "./sync_folder", "/shared_folder"
  end

  # Конфигурация для запуска ВМ на ubuntu
  # CLI: vagrant up ubuntu
  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "ubuntu/trusty64"
    ubuntu.vm.box_version = "20191107.0.0"
    ubuntu.vm.hostname = "ubuntuvm"
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    ubuntu.vm.network "private_network", ip: "192.168.33.11"
  end


  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = false

    # Customize the amount of memory on the VM:
    # vb.memory = "1024"
  end
end

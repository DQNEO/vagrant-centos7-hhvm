# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # my original box with chef installed
  config.vm.box = "centos6.5chef"
  # chef official box wihout chef installed :(
  #config.vm.box = "chef/centos-6.5"
  config.vm.network :private_network, ip: "10.10.10.10"
end

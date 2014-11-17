# -*- mode: ruby -*-
VAGRANTFILE_API_VERSION = "2"

# SHELL PROVISIONER
# https://docs.vagrantup.com/v2/provisioning/shell.html

$script = <<EOT
yum update -y

# epel
rpm -Uvh http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm

# docker-io
yum install -y docker-io

# httpd
#yum install httpd
EOT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # my original box with chef installed
  config.vm.box = "chef/centos-6.6"
  # chef official box wihout chef installed :(
  #config.vm.box = "chef/centos-6.5"
  config.vm.network :private_network, ip: "10.10.10.10"

  config.vm.provision "shell", inline: $script

end

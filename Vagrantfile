# -*- mode: ruby -*-
# SHELL PROVISIONER
# https://docs.vagrantup.com/v2/provisioning/shell.html

$script = <<EOT
  #yum update -y
 yum install -y epel-release

 rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
 rpm -Uvh http://yum.gleez.com/6/x86_64/gleez-repo-6-0.el6.noarch.rpm
 sed -i 's|baseurl=http://yum.gleez.com/6/$basearch/|baseurl=http://yum.gleez.com/7/$basearch/|g' /etc/yum.repos.d/gleez.repo
 yum --nogpgcheck -y install hhvm

 hhvm --version
EOT

Vagrant.configure("2") do |config|
  config.vm.box = "chef/centos-7.0"

  config.vm.network :private_network, ip: "10.10.10.10"

  config.vm.provision "shell", inline: $script

  config.vbguest.auto_update = false

  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end

end

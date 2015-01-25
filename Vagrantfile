# -*- mode: ruby -*-
VAGRANTFILE_API_VERSION = "2"

# SHELL PROVISIONER
# https://docs.vagrantup.com/v2/provisioning/shell.html

$script = <<EOT
yum update -y

# epel
#rpm -Uvh http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm

yum install -y epel-release

# MUST packages
yum install -y strace tree nano zsh rsync openssh-clients sysstat dstat tcpdum

# dev tools
yum install -y gcc make gdb man man-pages telnet colordiff screen

# docker
yum install -y docker

# httpd
#yum install -y httpd

## nginx
# rpm -Uvh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
# yum install --enablerepo=nginx -y nginx

# TC
#yum install -y tokyocabinet

# memcachdd
#yum install -y memcached


# mod_orz
# yum install -y http-devel

EOT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "chef/centos-7.0"

  config.vm.network :private_network, ip: "10.10.10.10"

  config.vm.provision "shell", inline: $script

end

# -*- mode: ruby -*-
# vi: set ft=ruby :

VBOX = "ubuntu/precise64"

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = VBOX
  config.vm.network "public_network"

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", 2048]   # set memory here
    v.customize ["modifyvm", :id, "--cpus", 2 ]       # set cores here
  end

  config.vm.provision "shell" do |s|
    s.inline = "wget --quiet -O - https://raw.github.com/sans-dfir/sift-bootstrap/master/bootstrap.sh | sudo bash -s --"
    # args
    # s = skin apply
    # y = all yes
    # i = install
    s.args   = "-s -y -i"
  end
end
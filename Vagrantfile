# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |vbox|
    vbox.customize ["modifyvm", :id, "--natdnsproxy1", "off"]
    vbox.customize ["modifyvm", :id, "--natdnshostresolver1", "off"]
    vbox.customize ["modifyvm", :id, "--nic2", "intnet"]
    vbox.customize ["modifyvm", :id, "--intnet2", "internal_network"]
  end

  config.vm.define :ubuntu_xenial do |ubuntu|
    ubuntu.vm.provider "virtualbox" do |vbox|
      vbox.memory = "1024"
      vbox.cpus   = 4
    end
    ubuntu.vm.box = "puppetlabs/ubuntu-16.04-64-nocm"
    ubuntu.vm.network "private_network", ip: "192.168.98.202"

    ubuntu.vm.provision "shell", inline: (<<-SHELL).gsub(/^ {4}/m, "")
      set -x
      export DEBIAN_FRONTEND=noninteractive
      if ! test -f /vagrant/.setup-done; then
        apt-get -y update
        apt-get -y install \
          util-linux \
          cgroup-lite \
          ruby \
          tmux
      fi
      touch /vagrant/.setup-done
    SHELL

    ubuntu.vm.network "private_network", ip: "192.168.98.1"
  end
end

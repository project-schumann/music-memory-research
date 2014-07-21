# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "hashicorp/precise64"

    config.vm.network "forwarded_port", guest: 8888, host: 8888

    config.vm.provision "shell", path: "https://raw.githubusercontent.com/patrickayoup/vagrant-shell-provisioner/master/src/ubuntu-14.04/installNativeCompiler.sh"
    config.vm.provision "shell", path: "https://raw.githubusercontent.com/patrickayoup/vagrant-shell-provisioner/master/src/ubuntu-14.04/installPython.sh"
end

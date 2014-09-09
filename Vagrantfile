# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "chef/ubuntu-14.04"
    config.ssh.forward_agent = true
    config.berkshelf.enabled = true
    config.omnibus.chef_version = :latest

    config.vm.network "forwarded_port", guest: 8888, host: 8888

    config.vm.provision "chef_solo" do |chef|

        # Allow any IP to connect to iPyNb and store notebooks in ./vagrant
        chef.json = {
            :ipynb => {
                :NotebookApp => {
                    :ip => "*"
                },
                :notebook_dir => "/vagrant/notebooks"
            }
        }

        chef.add_recipe "ipynb::default"
        chef.add_recipe "ipynb::virtenv_launch"
        chef.add_recipe "ipynb::proxy"
    end
end

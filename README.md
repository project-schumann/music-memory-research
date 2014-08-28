# Music-Memory

This research/prototype runs in an iPython Notebook under a virtual machine managed by vagrant.

To get started, be sure that both [Vagrant](http://www.vagrantup.com) and [Virtual Box](http://www.virtualbox.org) are installed on your computer.

Secondly, this virtual machine is provisioned using [Chef](http://www.getchef.com). The easiest way to get set up is to download the [ChefDK](http://downloads.getchef.com/chef-dk).

Once set up, from the root directory of this repository first run ``berks vendor`` to install the required cookbooks. Now to build the virtual machine run ``vagrant up``. This process may take some time to complete. Once completed you are ready to go and iPython Notebook should be running on the virtual machine. iPython Notebook runs on port 8888 which is forwarded to the host machine so to access the notebook, go to [http://localhost:8888](http://localhost:8888) and you should be ready to work. If by any chance port 8888 is already in use on your system, you may change this to another port in the Vagrantfile by changing the host parameter in the following line:

``config.vm.network "forwarded_port", guest: 8888, host: 8888``
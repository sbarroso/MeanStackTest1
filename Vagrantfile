# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "100.100.100.101"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  config.vm.synced_folder ".", "/vagrant"

  
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    # vb.gui = true

    #   # Customize the amount of memory on the VM:
    #   vb.memory = "1024"
  end

  config.vm.provision "ansible" do | ansible|
      #ansible.raw_arguments = "-i provisioning/hosts"
      #ansible.inventory_path = "hosts"
      ansible.playbook = "provisioning/main.yml"
  end
end

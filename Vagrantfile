# -*- mode: ruby -*-
# vi: set ft=ruby :

require "./dependency_manager"

check_plugins ["vagrant-hostsupdater", "vagrant-cachier"]


Vagrant.configure("2") do |config|

    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.hostname = "ecomputer-rocks.local"
    config.vm.synced_folder "src", "/var/www", :mount_options => ["dmode=777", "fmode=666"]

    config.vm.provision "shell", path: "bootstrap.sh"
    
    # Optional NFS. Make sure to remove other synced_folder line too
    #config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }

end

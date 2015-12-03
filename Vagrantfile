# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.hostname = "scotchbox"
    config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]
    

    config.vm.provision "shell", inline: <<-SHELL
        # Shell commands here...
	#apt-get install ssmtp
	cd /var/www/public
	rm index.php
	git clone https://github.com/hochla-simon/Pitter.git .
        echo "Hello, I will be printed on screen during Vagrant Up."
    SHELL

    # Optional NFS. Make sure to remove other synced_folder line too
    #config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }

end

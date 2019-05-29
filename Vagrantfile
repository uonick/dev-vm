# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

    config.vm.box = "ubuntu/bionic64"
    config.vm.box_check_update = true
    config.vm.hostname = "vagrant"
    config.vm.define "dev-vm"
    config.vm.provider :virtualbox do |vb|
        vb.name = "vagrant-dev-vm"
    end

    config.vm.network :forwarded_port, guest: 80, host: 8080
    config.vm.network :forwarded_port, guest: 3306, host: 3306
    config.vm.network :forwarded_port, guest: 6379, host: 6379

    config.vm.network "private_network", ip: "192.168.3.3"

    config.vm.provider :virtualbox do |v|
        v.customize ["modifyvm", :id, "--memory", "2048"]
        v.customize ["modifyvm", :id, "--vram", "16"]
    end

    # set project folder here:
    config.vm.synced_folder "./www","/code",
        owner: "vagrant",
        group: "www-data",
        mount_options: ["dmode=775,fmode=775"]

    # ansible
    config.ssh.insert_key = false
    config.vm.provision "ansible_local" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "playbook.yml"
    end
end

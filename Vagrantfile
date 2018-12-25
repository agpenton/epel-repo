# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "geerlingguy/centos7"
    config.vm.hostname = "test.studioone.am"
    config.vm.network :private_network, ip: "192.168.11.21"
    config.ssh.insert_key = false
    config.vm.provider :virtualbox do |v|
        v.customize ["modifyvm", :id, "--name", "test.dev"]
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--memory", 512]
        v.customize ["modifyvm", :id, "--cpus", 1]
        v.customize ["modifyvm", :id, "--ioapic", "on"]
    end

    # Enable provisioning with Ansible.
    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook.yml"
    end

end
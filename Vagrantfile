# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "zone1" do |zone1|
	  zone1.vm.box = "ubuntu/trusty64-juju"
	  zone1.vm.network :forwarded_port, guest: 22, host: 2122
      zone1.vm.network :forwarded_port, guest: 1247, host: 12470
	  zone1.vm.provision :ansible do |ansible|
		  ansible.playbook = "playbook_zone1.yaml"
	  end
	  zone1.vm.network "private_network", ip: "192.168.50.11"
	  zone1.vm.hostname = "irods1.irodsvagrant.org"
  end

  config.vm.define "zone2" do |zone2|
	  zone2.vm.box = "ubuntu/trusty64-juju"
	  zone2.vm.network :forwarded_port, guest: 22, host: 2123
      zone2.vm.network :forwarded_port, guest: 1247, host: 12471
	  zone2.vm.provision :ansible do |ansible|
		  ansible.playbook = "playbook_zone2.yaml"
	  end
	  zone2.vm.network "private_network", ip: "192.168.50.12"
	  zone2.vm.hostname = "irods2.irodsvagrant.org"
  end

end

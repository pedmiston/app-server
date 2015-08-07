# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "precise64"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.network :private_network, ip: "192.168.33.15"

  # Don't install this machine from github. Instead, sync from the submodule.
  config.vm.synced_folder "soundscapes", "/webapps/soundscapes/soundscapes-app/"

  config.vm.provision "ansible" do |ansible|
		ansible.playbook = "dev.yml"
		ansible.host_key_checking = false
		ansible.verbose = "v"
	end
end

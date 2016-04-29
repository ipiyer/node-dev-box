# -*- mode: ruby -*-

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network :forwarded_port, guest: 9000, host: 9000

  config.vm.network "private_network", ip: "192.168.33.10"

  #config.ssh.private_key_path = "~/.ssh/id_dsa1"

  config.vm.synced_folder "../", "/app"

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = true
    ansible.playbook = "site.yml"
     ansible.limit = "all"
    ansible.inventory_path = "ansible_hosts"
  end
end

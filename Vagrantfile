# -*- mode: ruby -*-
# vi: set ft=ruby :


VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.hostname = "elasticsearch"
  config.vm.network :forwarded_port, guest: 9300, host: 9300
  #config.vm.network :private_network, ip: "192.168.50.50"
  config.ssh.forward_agent = true

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "elasticsearch.yml"
    ansible.extra_vars = { user: "vagrant"}
  end

end

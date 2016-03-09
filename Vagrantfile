# -*- mode: ruby -*-
# vi: set ft=ruby :


VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    # Default Ubuntu Box
    #
    # This box is provided by Ubuntu vagrantcloud.com and is a nicely sized (332MB)
    # box containing the Ubuntu 14.04 Trusty 64 bit release. Once this box is downloaded
    # to your host computer, it is cached for future use under the specified box name.
    config.vm.box = "ubuntu/trusty64"

    # The Parallels Provider uses a different naming scheme.
    config.vm.provider :parallels do |v, override|
      override.vm.box = "parallels/ubuntu-14.04"
    end

    # The VMware Fusion Provider uses a different naming scheme.
    config.vm.provider :vmware_fusion do |v, override|
      override.vm.box = "netsensia/ubuntu-trusty64"
    end

    # VMWare Workstation can use the same package as Fusion
    config.vm.provider :vmware_workstation do |v, override|
      override.vm.box = "netsensia/ubuntu-trusty64"
    end

    # Hyper-V uses a different base box.
    config.vm.provider :hyperv do |v, override|
      override.vm.box = "ericmann/trusty64"
    end

  config.vm.hostname = "elasticsearch"
  config.vm.network :forwarded_port, guest: 9200, host: 9200
  config.ssh.forward_agent = true

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end

end

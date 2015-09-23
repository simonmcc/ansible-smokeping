# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.

  config.vm.define "precise64" do |precise64|
    precise64.vm.box = "hashicorp/precise64"

    precise64.vm.network "forwarded_port", guest: 8080, host: 8081

    precise64.vm.provision :ansible do |ansible|
      ansible.sudo = true
      ansible.playbook = "tests/test_role.yml"
      ansible.host_key_checking = false
      ansible.verbose = "v"
    end
  end

  config.vm.define "trusty64" do |trusty64|
    trusty64.vm.box = "ubuntu/trusty64"

    trusty64.vm.network "forwarded_port", guest: 8080, host: 8081

    trusty64.vm.provision :ansible do |ansible|
      ansible.sudo = true
      ansible.playbook = "tests/test_role.yml"
      ansible.host_key_checking = false
      ansible.verbose = "v"
    end
  end
end

# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "trusty32"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/20161205/trusty-server-cloudimg-i386-vagrant-disk1.box"
  config.vm.hostname = "djangoapp"
  config.vm.boot_timeout = 600

  config.vm.network :private_network, ip: "192.168.55.55"

  # ansible provision
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/deploy.yml"
    ansible.host_key_checking = false
    ansible.verbose = "vv"
  end
end

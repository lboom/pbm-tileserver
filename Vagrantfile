# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.define "tileserver"
  config.vm.box = "debian/buster64"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.synced_folder ".", "/vagrant",
    :mount_options => ["dmode=777,fmode=777"]

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "tileserver.yml"
  end
end

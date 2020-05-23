# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "kalilinux/rolling"

  config.vm.provider "virtualbox" do |v|
    v.name = "Provisioned Kali"
    v.memory = "4096"
    v.cpus = 1
    v.gui = false
  end

  config.vm.synced_folder "~/redteam", "/redteam"

  config.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.extra_vars = { ansible_python_interpreter:"/usr/bin/python3" }
   end
end

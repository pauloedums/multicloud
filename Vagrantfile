# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  ## Escolha da Box (Imagem)
  config.vm.box = "ubuntu/focal64"

  ## WORKSPACE
  config.vm.define 'multicloud' do |multicloud|
    multicloud.vm.hostname = "multicloud"

    # Configurações de Tamanho da VM
    multicloud.vm.provider "virtualbox" do |v|
      v.name = "multicloud"
      v.memory = 2048
      v.cpus = 2
    end

    # Instala o Ansible e faz as configurações da VM
    multicloud.vm.provision :ansible_local do |ansible|
        ansible.install_mode = "default"
        ansible.playbook = "playbook.yml"
        ansible.verbose  = true
        ansible.install  = true
        ansible.limit    = "all" 
        ansible.inventory_path = "inventory"
    end

  end

end

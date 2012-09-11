# -*- mode: ruby -*-
# vi: set ft=ruby :

domain = 'example.com'

Vagrant::Config.run do |config|
  config.vm.define :master do |master_config|
    master_config.vm.box = 'centos63'
    master_config.vm.box_url = 'https://dl.dropbox.com/u/7225008/Vagrant/CentOS-6.3-x86_64-minimal.box'
    master_config.vm.host_name = "puppet.#{domain}"
    master_config.vm.network :hostonly, '172.16.32.10'

    master_config.vm.provision :puppet do |puppet|
      puppet.manifests_path = 'provision/manifests'
      puppet.module_path = 'provision/modules'
    end
  end

  config.vm.define :client1 do |client_config|
    client_config.vm.box = 'centos63'
    client_config.vm.box_url = 'https://dl.dropbox.com/u/7225008/Vagrant/CentOS-6.3-x86_64-minimal.box'
    client_config.vm.host_name = "client1.#{domain}"
    client_config.vm.network :hostonly, '172.16.32.11'

    client_config.vm.provision :puppet do |puppet|
      puppet.manifests_path = 'provision/manifests'
      puppet.module_path = 'provision/modules'
    end
  end

  config.vm.define :client2 do |client_config|
    client_config.vm.box = 'centos63'
    client_config.vm.box_url = 'https://dl.dropbox.com/u/7225008/Vagrant/CentOS-6.3-x86_64-minimal.box'
    client_config.vm.host_name = "client2.#{domain}"
    client_config.vm.network :hostonly, '172.16.32.12'

    client_config.vm.provision :puppet do |puppet|
      puppet.manifests_path = 'provision/manifests'
      puppet.module_path = 'provision/modules'
    end
  end
end

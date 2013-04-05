# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "ubuntu-server-1204-x64"
  # config.vm.box_url = "http://domain.com/path/to/above.box"
  config.vm.network :hostonly, "192.168.33.10"
  config.vm.forward_port 80, 8080
  config.vm.share_folder "puppet_mount", "/puppet", "puppet"

  config.vm.provision :puppet do |puppet|
    puppet.options = "--verbose --debug"
    puppet.manifests_path = "puppet/manifests"
    puppet.module_path = "puppet/modules"
    puppet.manifest_file  = "site.pp"
  end

end

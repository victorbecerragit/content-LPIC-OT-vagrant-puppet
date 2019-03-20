Vagrant.configure("2") do |config|
  config.vm.define "web" do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.hostname = "web.vagrant.vm"
    web.vm.provision "shell" do |shell|
      shell.inline = "apt-get update -y"
      shell.inline = "apt-get install apache2 -y"
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/trusty64"
    db.vm.hostname = "db.vagrant.vm"
    db.vm.provision "puppet" do |puppet|
      puppet.manifests_path = "puppet/manifests"
      puppet.manifest_file = "default.pp"
      puppet.module_path = "puppet/modules"
      puppet.hiera_config_path = "puppet/hiera.yaml"
    end
  end
end

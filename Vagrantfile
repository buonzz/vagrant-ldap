Vagrant.configure("2") do |config|
  
  config.vm.box = "ubuntu/trusty64"

  if defined?(VagrantVbguest::Middleware)
    config.vbguest.auto_update = true
  end

  config.vm.network "private_network", ip: "192.168.34.62"
  config.vm.synced_folder "./", "/vagrant", id: "vagrant-root",
  owner: "vagrant",
  group: "vagrant",
  mount_options: ["dmode=775,fmode=664"]

  config.vm.network :forwarded_port, guest: 80, host: 80

  config.vm.provision :shell, :path => "provision.sh"
end

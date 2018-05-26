Vagrant.configure("2") do |config|
  config.vm.box = "jhcook/macos-sierra"
  # https://github.com/jonschipp/vagrant/issues/3#issuecomment-138215720
  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--usb", "on"]
    vb.customize ["modifyvm", :id, "--usbehci", "off"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "main.yml"
    ansible.compatibility_mode = "2.0"
  end
end

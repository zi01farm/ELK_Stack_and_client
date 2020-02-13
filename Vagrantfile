
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.define "client" do |client|
    client.vm.network "private_network", ip: "192.168.10.130"
    client.vm.provision "chef_solo" do |chef|
      chef.arguments = "--chef-license accept"
      chef.cookbooks_path = "Cookbooks"
      chef.add_recipe "client_cookbook::default"
    end
  end

  config.vm.define "ELK" do |elk|
    elk.vm.network "private_network", ip: "192.168.10.120"
    elk.vm.provision "chef_solo" do |chef|
      chef.arguments = "--chef-license accept"
      chef.cookbooks_path = "Cookbooks"
      chef.add_recipe "ELK_cookbook::default"
    end
  end



end

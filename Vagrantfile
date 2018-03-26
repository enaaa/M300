Vagrant.configure("2") do |config|
  config.vm.define "queen" do |subconfig|
    subconfig.vm.box = "bento/ubuntu-16.04"
	subconfig.vm.hostname = "queen"
	subconfig.vm.network :private_network, ip: "10.0.0.10"
  config.vm.provision "shell", inline: <<-SHELL
	sudo apt-get update
	sudo apt-get -y install apache2
	sudo apt -y install ufw
	sudo ufw enable
	sudo ufw allow 80/tcp
	sudo ufw allow 8080/tcp
  SHELL
  end
  
  config.vm.define "ena1" do |subconfig|
    subconfig.vm.box = "bento/ubuntu-16.04"
	subconfig.vm.hostname = "ena1"
	
	subconfig.vm.network :private_network, ip: "10.0.0.11"
  end


  config.vm.define "ena2" do |subconfig|
    subconfig.vm.box = "hashicorp/precise64"
	subconfig.vm.hostname = "ena2"
	subconfig.vm.network :private_network, ip: "10.0.0.13"
    end
	
  config.vm.provision "shell", inline: <<-SHELL
    apt-get install -y avahi-daemon libnss-mdns
  SHELL
end
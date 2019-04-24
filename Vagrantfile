
# author : Tasos Adamopoulos 
# email : adamopanast@gmail.com

Vagrant.configure("2") do |config|

# 	set vagrant box
	config.vm.box = "ubuntu/xenial64"

	config.vm.define "app" do |app|
		app.vm.network "private_network", ip: "192.168.33.20"
		# app01.vm.hostname "app01"
	end

# 	setup vm provisioner
	config.vm.provision "ansible" do |ansible|
		ansible.verbose = "v"
		ansible.playbook = "main.yml"

# 	setup ansible inventory groups
		# ansible.groups = {
		# 	"apps" => ["app"],
			
		# }
	end
end
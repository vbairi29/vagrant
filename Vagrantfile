Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "echo Hello"

  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
  config.vm.define "scriptbox" do |scriptbox|
	scriptbox.vm.box = "centos/7"
	scriptbox.vm.box_url = "centos/7"
	scriptbox.vm.hostname = "scriptbox"
	
	scriptbox.vm.network	"private_network" , ip: "192.168.56.110"
	
		
	scriptbox.vm.provider :virtualbox do |vb|
	 vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
     	 vb.customize ["modifyvm", :id, "--memory", 1024]
     	 vb.customize ["modifyvm", :id, "--name", "scriptbox"]
	 vb.linked_clone = true
	 end
  end
end

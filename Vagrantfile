Vagrant.configure("2") do |config|

	# create mgmt node
	config.vm.define :mgmt do |mgmt_config|
      mgmt_config.vm.box = "bertvv/centos72"
      mgmt_config.vm.hostname = "mgmt"
      mgmt_config.vm.network :private_network, ip: "10.0.15.10"
      mgmt_config.vm.provider "virtualbox" do |vb|
        vb.memory = "256"
      end
      mgmt_config.vm.provision :shell, path: "scripts/bootstrap-mgmt.sh"
  end

   # create web servers
  (1..2).each do |i|
    config.vm.define "web#{i}" do |node|
        node.vm.box = "bertvv/centos72"
        node.vm.hostname = "web#{i}"
        node.vm.network :private_network, ip: "10.0.15.2#{i}"
        node.vm.network "forwarded_port", guest: 80, host: "808#{i}"
        node.vm.provider "virtualbox" do |vb|
          vb.memory = "256"
        end
    end
  end
  
   #create load balancer
  config.vm.define :lb do |lb_config|
     lb_config.vm.box = "bertvv/centos72"
     lb_config.vm.hostname = "lb"
      lb_config.vm.network :private_network, ip: "10.0.15.11"
      lb_config.vm.network "forwarded_port", guest: 80, host: 8080
      lb_config.vm.provider "virtualbox" do |vb|
       vb.memory = "256"
     end
  end

  #config.vm.define :db do |db_config|
  #    db_config.vm.box = "bertvv/centos72"
  #    db_config.vm.network :private_network, ip: "10.0.15.26"
  #end

  #config.vm.define :file do |file_config|
  #    file_config.vm.box = "bertvv/centos72"
  #    file_config.vm.network :private_network, ip: "10.0.15.27"
  #end

  #config.vm.define :nagios do |nagios_config|
  #    nagios_config.vm.box = "bertvv/centos72"
  #    nagios_config.vm.network :private_network, ip: "10.0.15.15"
  #end

end
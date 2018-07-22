Vagrant.configure("2") do |config|

    config.vm.define "web1" do |web1|
    web1.vm.box = "puppetlabs/ubuntu-14.04-64-nocm"
    web1.vm.hostname = 'web1'
    web1.vm.box_url = "puppetlabs/ubuntu-14.04-64-nocm"

    web1.vm.network :private_network, ip: "192.168.56.101"
    web1.vm.network :forwarded_port, guest: 80, host: 8080
    web1.vm.provision "ansible" do |ansible|
    ansible.playbook = "AutomationLogic.yml"

    end
    end

    config.vm.define "web2" do |web2|
    web2.vm.box = "puppetlabs/ubuntu-14.04-64-nocm"
    web2.vm.hostname = 'web2'
    web2.vm.box_url = "puppetlabs/ubuntu-14.04-64-nocm"

    web2.vm.network :private_network, ip: "192.168.56.102"
    web2.vm.network :forwarded_port, guest: 80, host: 8081
    web2.vm.provision "ansible" do |ansible|
    ansible.playbook = "AutomationLogic.yml" 
    
    end
    end   
    
    config.vm.define "lb1" do |lb1|
    lb1.vm.box = "puppetlabs/ubuntu-14.04-64-nocm"
    lb1.vm.hostname = 'lb1'
    lb1.vm.box_url = "puppetlabs/ubuntu-14.04-64-nocm"

    lb1.vm.network :private_network, ip: "192.168.56.103"
    lb1.vm.network :forwarded_port, guest: 80, host: 8082
    lb1.vm.provision "ansible" do |ansible|
    ansible.playbook = "AutomationLogicLB.yml"

    end
    end 
end


Vagrant.configure("2") do |config|

  config.vm.define :server1 do |server1|
    server1.vm.box = "bento/centos-7.9"
    server1.vm.network :private_network, ip: "192.168.100.4"
    server1.vm.network :private_network, ip: "209.168.100.4"
    #server1.vm.network "public_network", ip: "192.168.0.14"
    server1.vm.network :forwarded_port, guest: 443, host:6443
    server1.vm.network :forwarded_port, guest: 80, host:6080
    server1.vm.hostname = "server1"
    server1.vm.provision "shell", path: "./scripts/server1.sh"
  end

  config.vm.define :server2 do |server2|
    server2.vm.box = "bento/centos-7.9"
    server2.vm.network :private_network, ip: "192.168.100.2"
    server2.vm.hostname = "server2"
    server2.vm.provision "shell", path: "./scripts/server2.sh"
  end

  config.vm.define :server3 do |server3|
    server3.vm.box = "bento/centos-7.9"
    server3.vm.network :private_network, ip: "192.168.100.3"
    server3.vm.hostname = "server3"
    server3.vm.provision "shell", path: "./scripts/server3.sh"
  end

  config.vm.define :firewall2 do |firewall2|
    firewall2.vm.box = "bento/centos-7.9"
    firewall2.vm.network :private_network, ip: "192.168.100.5"
    firewall2.vm.hostname = "firewall2"
  end

end

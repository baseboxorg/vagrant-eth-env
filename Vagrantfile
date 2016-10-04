Vagrant.configure("2") do |config|
  config.vm.define "ethereum" do |ethereum|
    ethereum.vm.box = "boxcutter/ubuntu1604"
    ethereum.vm.network "private_network", type: "dhcp"
    ethereum.vm.network :forwarded_port, guest: 8545, host: 8545
    ethereum.vm.network :forwarded_port, guest: 30303, host: 30303, protocol: "udp"
    
    ethereum.vm.provider "vmware_fusion" do |v|
      v.vmx["memsize"] = "2048"
      v.vmx["numvcpus"] = "2"
    end

    ethereum.vm.provision "shell", path: "configure-parity.sh"
  end
end



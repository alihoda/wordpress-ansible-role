ENV["LC_ALL"] = "en_US.UTF-8"

Vagrant.configure("2") do |config|
    config.vm.box = "debian/bookworm64"

    config.vm.define "server-1" do |node|
        node.vm.hostname = "server-1"
        node.vm.network "private_network", ip: "192.168.57.10"
        node.vm.provider "virtualbox" do |vb|
            vb.cpus = 2
            vb.memory = 2048
        end
    end
end

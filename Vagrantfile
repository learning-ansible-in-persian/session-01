Vagrant.configure("2") do |config|
  (1..10).each do |i|
    config.vm.define "ansible#{i}" do |node|
      node.vm.box = "bento/ubuntu-24.04"
      node.vm.hostname = "ansible#{i}"

      node.vm.network "private_network", ip: "192.168.56.1#{i}"

      node.vm.provider "virtualbox" do |vb|
        vb.name   = "ansible#{i}"
        vb.memory = 1024
        vb.cpus   = 1
      end

      node.vm.synced_folder ".", "/home/vagrant/host"
    end
  end
end

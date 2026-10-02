Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  # ===============================
  config.vm.define "control" do |control|
    control.vm.hostname = "control"
    control.vm.network "private_network", ip: "192.168.56.10"
    control.vm.provider "virtualbox" do |v|
      v.name = "ansible-control"
      v.memory = "1536"
      v.cpus = 1
    end
  end

   # =============================== 1 
  config.vm.define "target1" do |t1|
    t1.vm.hostname = "target1"
    t1.vm.network "private_network", ip: "192.168.56.11"
    t1.vm.provider "virtualbox" do |v|
      v.name = "ansible-target1"
      v.memory = "1024"
      v.cpus = 1
    end
  end

   # =============================== 2 
  config.vm.define "target2" do |t2|
    t2.vm.hostname = "target2"
    t2.vm.network "private_network", ip: "192.168.56.12"
    t2.vm.provider "virtualbox" do |v|
      v.name = "ansible-target2"
      v.memory = "1024"
      v.cpus = 1
    end
  end
end

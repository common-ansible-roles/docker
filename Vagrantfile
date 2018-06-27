Vagrant.configure("2") do |config|
  N = 5

  (1..N).each do |machine_id|
    if machine_id == 1
      config.vm.define "centos-7" do |machine|
        machine.vm.box = "centos/7"
        machine.vm.hostname = "centos-7"
        machine.vm.network "private_network", ip: "192.168.77.#{20+machine_id}"
      end
    end

    if machine_id == 2
      config.vm.define "debian-jessie" do |machine|
        machine.vm.box = "debian/jessie64"
        machine.vm.hostname = "debian-jessie"
        machine.vm.network "private_network", ip: "192.168.77.#{20+machine_id}"
      end
    end

    if machine_id == 3
      config.vm.define "debian-stretch" do |machine|
        machine.vm.box = "debian/stretch64"
        machine.vm.hostname = "debian-stretch"
        machine.vm.network "private_network", ip: "192.168.77.#{20+machine_id}"
      end
    end

    if machine_id == 4
      config.vm.define "ubuntu-xenial" do |machine|
        machine.vm.box = "ubuntu/xenial64"
        machine.vm.hostname = "ubuntu-xenial"
        machine.vm.network "private_network", ip: "192.168.77.#{20+machine_id}"

        config.vm.provision "shell" do |s|
          s.inline = "apt-get update && apt-get install -y python"
        end
      end
    end

    if machine_id == 5
      config.vm.define "ubuntu-bionic" do |machine|
        machine.vm.box = "ubuntu/bionic64"
        machine.vm.hostname = "ubuntu-bionic"
        machine.vm.network "private_network", ip: "192.168.77.#{20+machine_id}"

        config.vm.provision "shell" do |s|
          s.inline = "apt-get update && apt-get install -y python"
        end

        machine.vm.provision :ansible do |ansible|
          ansible.limit = "all"
          ansible.playbook = "vagrant.yml"
        end
      end
    end
  end
end

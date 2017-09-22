Vagrant.configure(2) do |config|
  # Development box
  config.vm.define "devbuntu" do |dev|
    # Select the box
    dev.vm.box = "bento/ubuntu-16.04"

    # Forward SSH agent
    dev.ssh.forward_agent = true

    # Setup shared project directory
    dev.vm.synced_folder "../", "/home/zeestrat/dev", owner: "10000", group: "50"

    # Private IP
    dev.vm.network "private_network", ip: "192.168.60.60"

    # Run playbook
    dev.vm.provision "ansible" do |ansible|
      ansible.playbook = "vagrant.yaml"
    end

    dev.vm.provider "virtualbox" do |vbox|
      vbox.memory = 4096
      vbox.cpus = 1
    end
  end
end

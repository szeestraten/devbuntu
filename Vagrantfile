Vagrant.configure(2) do |config|
  config.vm.define "devbuntu-bionic", primary: true do |dev|
    # Select the box
    dev.vm.box = "bento/ubuntu-18.04"

    # Forward SSH agent
    dev.ssh.forward_agent = true

    # Port forward
    dev.vm.network "forwarded_port", guest: 8080, host: 8080

    # Shared folder
    dev.vm.synced_folder "../", "/home/zeestrat/dev", owner: "10000", group: "50"

    # Disable default shared folder
    dev.vm.synced_folder ".", "/vagrant", disabled: true

    # Run playbook
    dev.vm.provision "ansible" do |ansible|
      ansible.playbook = "vagrant.yaml"
    end

    # Configure virtualbox
    dev.vm.provider "virtualbox" do |vbox|
      vbox.memory = 4096
      vbox.cpus = 2
    end
  end

  config.vm.define "devbuntu-xenial", autostart: false do |dev|
    # Select the box
    dev.vm.box = "bento/ubuntu-16.04"

    # Forward SSH agent
    dev.ssh.forward_agent = true

    # Port forward
    dev.vm.network "forwarded_port", guest: 8080, host: 8080

    # Shared folder
    dev.vm.synced_folder "../", "/home/zeestrat/dev", owner: "10000", group: "50"

    # Disable default shared folder
    dev.vm.synced_folder ".", "/vagrant", disabled: true

    # Run playbook
    dev.vm.provision "ansible" do |ansible|
      ansible.playbook = "vagrant.yaml"
    end

    # Configure virtualbox
    dev.vm.provider "virtualbox" do |vbox|
      vbox.memory = 4096
      vbox.cpus = 2
    end
  end
end

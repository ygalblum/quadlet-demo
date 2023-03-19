Vagrant.configure("2") do |config|

  # name the VM
  config.vm.define "quadlet-demo" do |node|

    # which image to use
    node.vm.box = "generic/centos9s"

    # disable synced folders
    node.vm.synced_folder ".", "/vagrant", disabled: true

    # sizing of the VMs
    node.vm.provider "libvirt" do |lv|
      lv.random_hostname = false
      lv.memory = 2048
      lv.cpus = 2
    end

    # set the hostname
    node.vm.hostname = "quadlet-demo"

    node.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "playbook.yml"
    end # node.vm.provision

  end # config.vm.define nodes

end

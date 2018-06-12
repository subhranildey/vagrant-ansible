VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "debian/stretch64"
  config.disksize.size = "20GB"
  config.vm.network "private_network", ip: "10.0.0.2"
  config.ssh.forward_agent = true
  config.vm.host_name = "dev.dmn.lcl"
  config.vm.provider "virtualbox" do |vb|
  #config.vm.synced_folder "/Users/sdey/DRG", "/home/sdey/DRG", type: "nfs"
  #config.vm.synced_folder ".ssh", "/home/sdey/.ssh", type: "nfs"
    vb.memory = "4096"
    vb.cpus = "2"
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end
end

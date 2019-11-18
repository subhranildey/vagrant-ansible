VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "debian/buster64"
  config.disksize.size = "20GB"
  config.vm.network "public_network", bridge: "wlp2s0", ip: "192.168.1.9"
  config.ssh.forward_agent = true
  config.vm.host_name = "dev.dmn.lcl"
  config.vm.provider "virtualbox" do |vb|
      vb.memory = "4096"
      vb.cpus = "2"
      vb.name = "Debian10"
    if ENV['FIRST_RUN'] == 'true'
      config.vbguest.auto_update = false
      config.vm.synced_folder "/home/sdey/VM-Share", "/home/sdey/VM-Share",  mount_options: ["dmode=770,fmode=660"], disabled: true
    else
      config.vm.synced_folder "/home/sdey/VM-Share", "/home/sdey/VM-Share",  mount_options: ["dmode=770,fmode=660"]
#    end
      config.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook.yml"
end
  end
end
end

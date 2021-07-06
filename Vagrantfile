# -*- mode: ruby -*-

Vagrant.configure("2") do |config|
  config.vm.define "rt-pfsense" do |rtpfsense|
    rtpfsense.vm.box = "kennyl/pfsense"
    rtpfsense.vm.hostname = "rt-pfsense"
    rtpfsense.vm.box_version = "2.4.0"
    rtpfsense.vm.synced_folder ".", "/vagrant", disabled: true
    rtpfsense.vm.network "private_network", virtualbox__intnet: "LAN1", ip: "192.168.1.1"
    rtpfsense.vm.provider "virtualbox" do |vb|
      vb.name = "rt-pfsense"
      vb.cpus = "2"
      vb.memory = "2048"
    end
  end
  config.vm.define "cl1" do |cl1|
    cl1.vm.box = "peru/ubuntu-20.04-desktop-amd64"
    cl1.vm.box_version = "20210701.01"
    cl1.vm.hostname = "cl1"
    cl1.vm.network "private_network", virtualbox__intnet: "LAN1", type: "dhcp"
    cl1.vm.provider "virtualbox" do |vb|
      vb.name = "cl1"
      vb.cpus = "2"
      vb.memory = "4096"
      vb.gui = true
    end
  end
end

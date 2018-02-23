# Defines our Vagrant environment
#
# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX_IMAGE = "ubuntu/xenial64" 
NODE_COUNT = 1

Vagrant.configure("2") do |config|
  
  config.vm.provider "virtualbox" do |v|
    #v.name = v.hostname
    v.memory = 666
    v.cpus = 1
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "25"]
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.define "nsxman" do |subconfig|     
    subconfig.vm.box = BOX_IMAGE     
    subconfig.vm.hostname = "nsxman"     
    subconfig.vm.network :private_network, ip: "10.0.0.10" 
  end     
  
  #(1..NODE_COUNT).each do |i|     
    #config.vm.define "node#{i}" do |subconfig|       
      #subconfig.vm.box = BOX_IMAGE       
      #subconfig.vm.hostname = "node#{i}"       
      #subconfig.vm.network :private_network, ip: "10.0.0.#{i + 10}"
    #end   
  #end   
  
  
end

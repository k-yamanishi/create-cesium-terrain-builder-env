# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.box_url = "https://app.vagrantup.com/centos/boxes/7"
  config.proxy.http = "http://kanki-hirose:KanKi1022@172.16.1.11:8080"
  config.proxy.https = "https://kanki-hirose:KanKi1022@172.16.1.11:8080"
  config.proxy.no_proxy = "localhost,127.0.0.1"
  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
    vb.memory = 1024
  end

  config.vm.define "builder" do |server|
    server.vm.hostname = "builder"
    server.vm.network "forwarded_port", guest: 80, host: 10080
    server.vm.network "forwarded_port", guest: 1337, host: 10000
    server.vm.network "forwarded_port", guest: 5432, host: 15432
    server.vm.network "forwarded_port", guest: 4848, host: 14848
    server.vm.network "forwarded_port", guest: 8080, host: 18080
  end
end

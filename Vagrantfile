# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.box = 'javabudd/centos72-samba'
  config.ssh.pty = true
  config.vm.network "private_network", ip: "192.168.69.69"
#  config.vm.synced_folder ".", "/vagrant", type: "smb", mount_options: ["dir_mode=0777,file_mode=0777"]

  config.vm.provision "docker", run: "always" do |d|
    d.build_image "/vagrant/containers/web",
      args: "-t 'web'"

    d.run "web",
      args: "--name web --restart no -p 80:80 -p 443:443 -v '/vagrant/app:/usr/share/nginx/html'"
  end
end
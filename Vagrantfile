config.vm.box = "geerlingguy/ubuntu2004"

config.vm.network "forwarded_port", guest: 3000, host: 3000, protocol: "tcp"
config.vm.network "forwarded_port", guest: 5000, host: 5000, protocol: "tcp"  
config.vm.boot_timeout = 600
config.vm.provider "virtualbox" do |vb|
  vb.gui = true
@@ -23,8 +27,7 @@ Vagrant.configure("2") do |config|
 config.vm.provision :ansible do |ansible|
  ansible.playbook = "playbook.yml"
end  
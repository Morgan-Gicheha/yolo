
Vagrant.configure("2") do |config|
   config.vm.box = "geerlingguy/ubuntu2004"

  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 5000, host: 5000
  config.vm.network "forwarded_port", guest: 27017, host: 27017

   config.vm.synced_folder ".", "/vagrant"

   config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y ansible docker.io
    sudo usermod -aG docker vagrant
  SHELL

   config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
     ansible.extra_vars = {
      ansible_python_interpreter: "/usr/bin/python3"
    }
  end

end
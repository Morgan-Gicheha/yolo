Vagrant.configure("2") do |config|
   config.vm.box = "geerlingguy/ubuntu2004"

   config.vm.network "private_network", type: "dhcp"


  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "hosts.ini"  
    ansible.become = true
  end
end

Vagrant.configure("2") do |config|
  config.vm.box = "generic/arch"

  config.vm.provision "shell", run: "always", inline: "sudo rm -rf /usr/share/ansible/roles/arch-base || true && sudo mkdir -p /usr/share/ansible/roles && sudo cp -r /vagrant /usr/share/ansible/roles/arch-base"

  config.vm.provision "ansible_local", run: "always" do |ansible|
    ansible.playbook = "tests/test.yml"
  end
end

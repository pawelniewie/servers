Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/trusty64"

    config.vm.network "forwarded_port", guest: 80, host: 8080

    config.vm.provision "ansible" do |ansible|
        ansible.groups = {
          'database' => ['default']
        }

        ansible.playbook = "vagrant.yml"
        ansible.ask_vault_pass = true
    end
end

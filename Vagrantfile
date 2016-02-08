Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/trusty64"

    config.vm.network "forwarded_port", guest: 80, host: 8080

    config.vm.provision "ansible" do |ansible|
        ansible.groups = {
          'proxy' => ['default']
        }

        ansible.playbook = "playbook.yml"
    end
end

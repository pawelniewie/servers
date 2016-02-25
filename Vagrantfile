unless Vagrant.has_plugin?("vagrant-hostsupdater")
    puts "first you need to run: vagrant plugin install vagrant-hostsupdater"
else
		Vagrant.configure("2") do |config|
		    config.vm.box = "ubuntu/trusty64"

		    config.vm.network :private_network, ip: "192.168.3.11"
        # config.vm.hostname = "database.usezent.it"
        # config.hostsupdater.aliases = ["www.spartez.com"]

		    config.vm.provision "ansible" do |ansible|
		        ansible.groups = {
		          'database' => ['default']
		        }

		        ansible.playbook = "playbook.yml"
		        ansible.ask_vault_pass = true
		        ansible.extra_vars = { machine: 'vagrant' }
		    end
		end
end
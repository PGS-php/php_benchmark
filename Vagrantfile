ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'
Vagrant.configure("2") do |config|
  config.vm.define "php56" do |php56|
      php56.vm.box = "debian/jessie64"

      php56.vm.network :private_network, ip: "10.0.0.201"
      php56.ssh.forward_agent = true

      php56.vm.network "forwarded_port", guest: 80, host: 5656

      # Customize your VM parameters
      php56.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        vb.customize ["modifyvm", :id, "--memory", 512]
        #vb.customize ["modifyvm", :id, "--name", "php56"]
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
        php56.vm.post_up_message = "App on PHP 5.6: 10.0.0.201 (http://127.0.0.1:5656/app_dev.php)"
      end

      php56.vm.synced_folder "./symfony", "/var/www/current/active", id: "vagrant-root", type: "nfs"

      php56.vm.provision "pre", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/pre-book.yml"
      end

      php56.vm.provision "php56", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/php56.yml"
      end

      php56.vm.provision "post", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/post-book.yml"
      end

      php56.vm.provision "symfony-install", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/symfony-install.yml"
      end
  end

  config.vm.define "php71" do |php71|
      php71.vm.box = "debian/jessie64"

      php71.vm.network :private_network, ip: "10.0.0.202"
      php71.ssh.forward_agent = true

      php71.vm.network "forwarded_port", guest: 80, host: 7171

      # Customize your VM parameters
      php71.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        vb.customize ["modifyvm", :id, "--memory", 512]
        #vb.customize ["modifyvm", :id, "--name", "php71"]
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
        php71.vm.post_up_message = "App on PHP 7.1: 10.0.0.202 (http://127.0.0.1:7171/app_dev.php)"
      end

      php71.vm.synced_folder "./symfony", "/var/www/current/active", id: "vagrant-root", type: "nfs"

      php71.vm.provision "pre", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/pre-book.yml"
      end

      php71.vm.provision "php71", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/php71.yml"
      end

      php71.vm.provision "post", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/post-book.yml"
      end

      php71.vm.provision "symfony-install", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/symfony-install.yml"
      end
  end

  config.vm.define "bench" do |bench|
      bench.vm.box = "debian/jessie64"

      bench.vm.network :private_network, ip: "10.0.0.203"
      bench.ssh.forward_agent = true

      # Customize your VM parameters
      bench.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        vb.customize ["modifyvm", :id, "--memory", 1024]
        #vb.customize ["modifyvm", :id, "--name", "bench"]
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
        bench.vm.post_up_message = "Access to benchmark node: vagrant ssh bench"
      end

      bench.vm.provision "bench", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/bench.yml"
      end
  end
end

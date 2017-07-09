ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'
Vagrant.configure("2") do |config|

  config.vm.define "php56_nginx" do |php56_nginx|
      php56_nginx.vm.box = "ubuntu/xenial64"

      php56_nginx.vm.network :private_network, ip: "10.0.0.201"
      php56_nginx.ssh.forward_agent = true

      php56_nginx.vm.network "forwarded_port", guest: 80, host: 5656

      # Customize your VM parameters
      php56_nginx.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        vb.customize ["modifyvm", :id, "--memory", 512]
        #vb.customize ["modifyvm", :id, "--name", "php56_nginx"]
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
        php56_nginx.vm.post_up_message = "App on PHP 5.6: 10.0.0.201 (http://127.0.0.1:5656/app_dev.php)"
      end

      php56_nginx.vm.synced_folder "./symfony", "/var/www/current/active", id: "vagrant-root", type: "nfs"

      php56_nginx.vm.provision "pre", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/pre-book.yml"
      end

      php56_nginx.vm.provision "php56_nginx", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/php56_nginx.yml"
      end

      php56_nginx.vm.provision "post", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/post-book.yml"
      end

      php56_nginx.vm.provision "symfony-install", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/symfony-install.yml"
      end
  end

  config.vm.define "php71_nginx" do |php71_nginx|
      php71_nginx.vm.box = "ubuntu/xenial64"

      php71_nginx.vm.network :private_network, ip: "10.0.0.202"
      php71_nginx.ssh.forward_agent = true

      php71_nginx.vm.network "forwarded_port", guest: 80, host: 7171

      # Customize your VM parameters
      php71_nginx.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        vb.customize ["modifyvm", :id, "--memory", 512]
        #vb.customize ["modifyvm", :id, "--name", "php71_nginx"]
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
        php71_nginx.vm.post_up_message = "App on PHP 7.1: 10.0.0.202 (http://127.0.0.1:7171/app_dev.php)"
      end

      php71_nginx.vm.synced_folder "./symfony", "/var/www/current/active", id: "vagrant-root", type: "nfs"

      php71_nginx.vm.provision "pre", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/pre-book.yml"
      end

      php71_nginx.vm.provision "php71_nginx", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/php71_nginx.yml"
      end

      php71_nginx.vm.provision "post", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/post-book.yml"
      end

      php71_nginx.vm.provision "symfony-install", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/symfony-install.yml"
      end
  end

  config.vm.define "php56_apache" do |php56_apache|
      php56_apache.vm.box = "ubuntu/xenial64"

      php56_apache.vm.network :private_network, ip: "10.0.0.203"
      php56_apache.ssh.forward_agent = true

      php56_apache.vm.network "forwarded_port", guest: 80, host: 5757

      # Customize your VM parameters
      php56_apache.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        vb.customize ["modifyvm", :id, "--memory", 512]
        #vb.customize ["modifyvm", :id, "--name", "php56_apache"]
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
        php56_apache.vm.post_up_message = "App on PHP 5.6: 10.0.0.203 (http://127.0.0.1:5757/app_dev.php)"
      end

      php56_apache.vm.synced_folder "./symfony", "/var/www/current/active", id: "vagrant-root", type: "nfs"

      php56_apache.vm.provision "pre", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/pre-book.yml"
      end

      php56_apache.vm.provision "php56_apache", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/php56_apache.yml"
      end

      php56_apache.vm.provision "post", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/post-book.yml"
      end

      php56_apache.vm.provision "symfony-install", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/symfony-install.yml"
      end
  end

  config.vm.define "php71_apache" do |php71_apache|
      php71_apache.vm.box = "ubuntu/xenial64"

      php71_apache.vm.network :private_network, ip: "10.0.0.204"
      php71_apache.ssh.forward_agent = true

      php71_apache.vm.network "forwarded_port", guest: 80, host: 7272

      # Customize your VM parameters
      php71_apache.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        vb.customize ["modifyvm", :id, "--memory", 512]
        #vb.customize ["modifyvm", :id, "--name", "php71_apache"]
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
        php71_apache.vm.post_up_message = "App on PHP 7.1: 10.0.0.204 (http://127.0.0.1:7272/app_dev.php)"
      end

      php71_apache.vm.synced_folder "./symfony", "/var/www/current/active", id: "vagrant-root", type: "nfs"

      php71_apache.vm.provision "pre", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/pre-book.yml"
      end

      php71_apache.vm.provision "php71_apache", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/php71_apache.yml"
      end

      php71_apache.vm.provision "post", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/post-book.yml"
      end

      php71_apache.vm.provision "symfony-install", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/symfony-install.yml"
      end
  end

  config.vm.define "bench" do |bench|
      bench.vm.box = "ubuntu/xenial64"

      bench.vm.network :private_network, ip: "10.0.0.205"
      bench.ssh.forward_agent = true

      # Customize your VM parameters
      bench.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        vb.customize ["modifyvm", :id, "--memory", 512]
        #vb.customize ["modifyvm", :id, "--name", "bench"]
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
        bench.vm.post_up_message = "Access to benchmark node: vagrant ssh bench"
      end

      config.vm.provision "shell", inline: "apt install python -y"

      bench.vm.provision "bench", type: "ansible" do |ansible|
        ansible.playbook = "provisioning/bench.yml"
      end
  end
end

Vagrant.configure("2") do |config|

    # Box configuration.
    config.vm.box       = "ubuntu/trusty64"

    # Network configuration.
    # port 80
    config.vm.network :forwarded_port, host: 8080, guest: 80
    # postgres - 9001
    config.vm.network :forwarded_port, guest: 9001, host: 9001
    # redis - 6379
    config.vm.network :forwarded_port, guest: 6379, host: 6379
    # mongodb - 27017
    config.vm.network :forwarded_port, guest: 27017, host: 27017
    # solr - 8983
    config.vm.network :forwarded_port, guest: 8983, host: 8983
    # VM ip address
    config.vm.network :private_network, ip: "192.168.50.50"
    # storage
    config.vm.synced_folder "app/storage", "/vagrant/app/storage", :owner => 'www-data', :group => 'www-data'

    # Vagrant memory
    config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 2
    end

    # Ansible provisioning.
    config.vm.provision :ansible do |ansible|
        ansible.limit           = "all"
        ansible.playbook        = "ansible/playbook.yml"
        ansible.inventory_path  = "ansible/ansible_hosts"
    end
end

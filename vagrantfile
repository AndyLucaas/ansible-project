Vagrant.configure("2") do |config|
  # Configuration de l'interface en mode pont (Bridge) avec la machine hôte
  bridge = "enp0s3" 

  # Serveur Ansible (Contrôleur)
  config.vm.define "ansible" do |ansible|
    ansible.vm.box = "debian/bookworm64"
    ansible.vm.hostname = "ansible"
    ansible.vm.network "private_network", ip: "192.168.56.10", bridge: bridge
    ansible.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
    # SSH et Ansible
    ansible.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y ansible openssh-server
      ssh-keygen -t rsa -f /home/vagrant/.ssh/id_rsa -N ''
      ssh-copy-id -i /home/vagrant/.ssh/id_rsa.pub vagrant@192.168.56.11
      ssh-copy-id -i /home/vagrant/.ssh/id_rsa.pub vagrant@192.168.56.12
      ssh-copy-id -i /home/vagrant/.ssh/id_rsa.pub vagrant@192.168.56.13
      ssh-copy-id -i /home/vagrant/.ssh/id_rsa.pub vagrant@192.168.56.14
      ssh-copy-id -i /home/vagrant/.ssh/id_rsa.pub vagrant@192.168.56.16
      ssh-copy-id -i /home/vagrant/.ssh/id_rsa.pub vagrant@192.168.56.17
    SHELL
  end

  # Serveur 1 (WEB Server1)
  config.vm.define "serveur1" do |serveur1|
    serveur1.vm.box = "debian/bookworm64"
    serveur1.vm.hostname = "serveur1"
    serveur1.vm.network "private_network", ip: "192.168.56.11", bridge: bridge
    serveur1.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
    # Provision SSH
    serveur1.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y openssh-server
      mkdir -p /home/vagrant/.ssh
    SHELL
  end

  # Serveur 2 (WEB Server2)
  config.vm.define "serveur2" do |serveur2|
    serveur2.vm.box = "debian/bookworm64"
    serveur2.vm.hostname = "serveur2"
    serveur2.vm.network "private_network", ip: "192.168.56.12", bridge: bridge
    serveur2.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
    # Provision SSH
    serveur2.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y openssh-server
      mkdir -p /home/vagrant/.ssh
    SHELL
  end

  # Serveur 3 (Monitoring)
  config.vm.define "serveur3" do |serveur3|
    serveur3.vm.box = "debian/bookworm64"
    serveur3.vm.hostname = "serveur3"
    serveur3.vm.network "private_network", ip: "192.168.56.13", bridge: bridge
    serveur3.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
    # Provision SSH
    serveur3.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y openssh-server
      mkdir -p /home/vagrant/.ssh
    SHELL
  end

  # Serveur 4 (autorite)
  config.vm.define "serveur4" do |serveur4|
    serveur4.vm.box = "debian/bookworm64"
    serveur4.vm.hostname = "serveur4"
    serveur4.vm.network "private_network", ip: "192.168.56.14", bridge: bridge
    serveur4.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
    # Provision SSH
    serveur4.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y openssh-server
      mkdir -p /home/vagrant/.ssh
    SHELL
  end
  
  # Serveur haproxy 1 et 2
  config.vm.define "haproxy" do |haproxy|
    haproxy.vm.box = "debian/bookworm64"
    haproxy.vm.hostname = "haproxy"
    haproxy.vm.network "private_network", ip: "192.168.56.16", bridge: bridge
    haproxy.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
    # Provision SSH
    haproxy.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y openssh-server
      mkdir -p /home/vagrant/.ssh
    SHELL
  end
  config.vm.define "haproxy2" do |haproxy2|
    haproxy2.vm.box = "debian/bookworm64"
    haproxy2.vm.hostname = "haproxy2"
    haproxy2.vm.network "private_network", ip: "192.168.56.17", bridge: bridge
    haproxy2.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
    # Provision SSH
    haproxy2.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y openssh-server
      mkdir -p /home/vagrant/.ssh
    SHELL
  end
end

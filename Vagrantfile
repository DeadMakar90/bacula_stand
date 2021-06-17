Vagrant.configure("2") do |config|
  config.vm.box = "smolensk-vanilla-gui/1.6.6"
  config.vm.box_url = "https://vault.astralinux.ru/vagrant/smolensk-vanilla-gui-1.6.6.json"

  config.vm.define "director" do |dir|
    dir.vm.network "public_network", ip: "192.168.0.5"
    dir.vm.hostname = "director"
    dir.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install -y vim mc 
    SHELL
    dir.vm.provider "virtualbox" do |vb|
      vb.cpus = "1"
      vb.memory = "1024"
      vb.name = "director"
     end
    end
  config.vm.define "storage" do |str|
    str.vm.network "public_network", ip: "192.168.0.6"
    str.vm.hostname = "storage"
    str.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install -y vim mc bacula-sd
    SHELL
    str.vm.provider "virtualbox" do |vb|
      vb.cpus = "1"
      vb.memory = "1024"
      vb.name = "storage"
    end
  end
  config.vm.define "client" do |cli|
    cli.vm.network "public_network", ip: "192.168.0.8"
    cli.vm.hostname = "client"
    cli.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install -y vim mc bacula-fd
    SHELL
    cli.vm.provider "virtualbox" do |vb|
      vb.cpus = "1"
      vb.memory = "1024"
      vb.name = "client"
    end
  end
   # config.vm.define "client2" do |cli2|
   # cli2.vm.network "public_network", ip: "192.168.0.8"
   # cli2.vm.hostname = "client"
   # cli2.vm.provision "shell", inline: <<-SHELL
   # apt update
   # apt install -y vim mc bacula-fd bach-completion
   # SHELL
   # cli2.vm.provider "virtualbox" do |vb|
   #   vb.cpus = "1"
   #   vb.memory = "1024"
   #   vb.name = "client2"
   # end
  #end
    config.vm.define "storage2" do |str2|
    str2.vm.network "public_network", ip: "192.168.0.7"
    str2.vm.hostname = "storage2"
    str2.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install -y vim mc bacula-sd bash-completion
    SHELL
    str2.vm.provider "virtualbox" do |vb|
      vb.cpus = "1"
      vb.memory = "1024"
      vb.name = "storage2"
    end
  end
end

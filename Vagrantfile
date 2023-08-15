Vagrant.configure("2") do |config|
  config.vm.define "rocky" do |rocky|
    rocky.vm.box = "generic/rocky8"  # Verifique a disponibilidade da imagem
    rocky.vm.network "private_network", type: "dhcp"
    rocky.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
  end

  config.vm.define "debian" do |debian|
    debian.vm.box = "debian/buster64"  # Verifique a disponibilidade da imagem
    debian.vm.network "private_network", type: "dhcp"
    debian.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
  end

  config.vm.define "windows" do |windows|
    windows.vm.box = "mwrock/Windows2016"  # Verifique a disponibilidade da imagem
    windows.vm.communicator = "winrm"
    windows.vm.network "private_network", type: "dhcp"
    windows.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
    windows.vm.guest = :windows
    windows.vm.provision "shell", inline: <<-SHELL
      # Comandos de provisionamento para Windows
    SHELL
  end
end

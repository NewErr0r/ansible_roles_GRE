Vagrant.configure("2") do |config|

#--------------------------------CentOS-----------------------------------------

    config.vm.define "centos" do |centos|
        centos.vm.hostname = "centos"
        centos.vm.box = "generic/centos8s"
        centos.vm.network "public_network", bridge: "br0", ip: "192.168.0.151"

        centos.vm.provider "virtualbox" do |vb|
            vb.name = "centos"
            vb.cpus = 1
            vb.memory = "1024"
        end

     centos.vm.provision "shell", inline: <<-SHELL
        sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
        systemctl restart sshd.service
        sudo echo "root:toor" | chpasswd
    SHELL
   end
#--------------------------------Debian-----------------------------------------

    config.vm.define "debian" do |debian|
        debian.vm.hostname = "debian"
        debian.vm.box = "generic/debian11"
        debian.vm.network "public_network", bridge: "br0", ip: "192.168.0.152"

        debian.vm.provider "virtualbox" do |vb|
           vb.name = "debian"
            vb.cpus = 1
            vb.memory = "1024"
        end

    debian.vm.provision "shell", inline: <<-SHELL
        sudo echo "root:toor" | chpasswd
    SHELL
   end
#--------------------------------Ubuntu-----------------------------------------

    config.vm.define "ubuntu" do |ubuntu|
        ubuntu.vm.hostname = "ubuntu"
        ubuntu.vm.box = "generic/ubuntu2004"
        ubuntu.vm.network "public_network", bridge: "br0", ip: "192.168.0.153"

        ubuntu.vm.provider "virtualbox" do |vb|
            vb.name = "ubuntu"
            vb.cpus = 1
            vb.memory = "1024"
        end

    ubuntu.vm.provision "shell", inline: <<-SHELL
        sudo echo "root:toor" | chpasswd
    SHELL
   end
##############################################################
end

Vagrant.configure("2") do |config|

  config.vm.box = "eurolinux-vagrant/centos-stream-9"
  config.vm.network "private_network", ip: "192.168.60.10"
  config.vm.network "public_network", bridge: "eno1"
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  config.vm.provision "shell", inline: <<-SHELL
    # Install required packages
    yum install httpd wget unzip vim -y

    # Start and enable Apache
    systemctl start httpd
    systemctl enable httpd

    # Download and deploy the Barista Cafe website
    mkdir -p /tmp/barista
    cd /tmp/barista
    wget https://www.tooplate.com/download/2137_barista_cafe
    mv 2137_barista_cafe 2137_barista_cafe.zip
    unzip -o 2137_barista_cafe.zip
    chown -R vagrant:vagrant 2137_barista_cafe
    rsync -av 2137_barista_cafe/* /var/www/html/

    # Restart Apache
    systemctl restart httpd

    # Clean up temporary files
    cd /tmp/
    rm -rf /tmp/barista
  SHELL

end

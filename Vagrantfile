$script = <<SCRIPT
  sudo apt-get update
  sudo apt-get install git -y && sudo apt-get install htop
  cd /home/vagrant && git clone https://github.com/selfup/DevOpsOne
  sudo /usr/sbin/update-locale LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8

SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision :shell, :inline => $script
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.synced_folder "~/Documents/rejs", "/home/vagrant/rejs"
  config.vm.synced_folder "~/Documents/reegbase", "/home/vagrant/reegbase"
  config.vm.synced_folder "~/Documents/idea_box_js", "/home/vagrant/idea_box_js"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end
end

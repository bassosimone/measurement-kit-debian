Vagrant.configure(2) do |config|
  config.vm.synced_folder ".", "/mk"
  config.vm.define "trusty64" do |trusty64|
    trusty64.vm.box = "ubuntu/trusty64"
    trusty64.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
    trusty64.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y autoconf automake autotools-dev \
        build-essential ca-certificates devscripts git libevent-dev \
        libssl-dev libgeoip-dev libtool lintian debhelper
    SHELL
  end
end

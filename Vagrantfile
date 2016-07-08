Vagrant.configure(2) do |config|
  config.vm.synced_folder ".", "/mk"
  config.vm.define "jessie64" do |jessie64|
    jessie64.vm.box = "debian/contrib-jessie64"
    jessie64.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
    jessie64.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y autoconf automake autotools-dev \
        build-essential ca-certificates devscripts git libevent-dev \
        libssl-dev libgeoip-dev libtool lintian
    SHELL
  end
end

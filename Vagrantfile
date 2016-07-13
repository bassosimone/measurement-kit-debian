Vagrant.configure(2) do |config|
  config.vm.synced_folder ".", "/mk"

  config.vm.define "build" do |build|
    build.vm.box = "debian/contrib-jessie64"
    build.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
    build.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y autotools-dev debhelper devscripts lintian
      sudo apt-get install -y libssl-dev libevent-dev libgeoip-dev
    SHELL
  end

  config.vm.define "trusty" do |trusty|
    trusty.vm.box = "ubuntu/trusty64"
    trusty.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y autotools-dev debhelper devscripts lintian
    SHELL
  end

  config.vm.define "jessie" do |jessie|
    jessie.vm.box = "debian/contrib-jessie64"
    jessie.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
    jessie.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y build-essential devscripts
      echo "deb-src http://ppa.launchpad.net/bassosimone/measurement-kit/ubuntu xenial main" \
        | sudo tee /etc/apt/sources.list.d/mk.list
      sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys A1A0E574EFACEE7B
      sudo apt-get update
    SHELL
  end

end

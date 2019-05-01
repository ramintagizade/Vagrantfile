if Vagrant::VERSION < "2.0.0"
  $stderr.puts "Must redirect to new repository for old Vagrant versions"
  Vagrant::DEFAULT_SERVER_URL.replace('https://vagrantcloud.com')
end

Vagrant.configure("2") do |config|
  config.vm.define :remote do |remote|
    remote.vm.box = "ubuntu/trusty64"
    remote.vm.network :private_network, ip: "192.168.31.100"
    remote.vm.hostname = "my.remote.vm"

    remote.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--cpus", "1", "--memory", 1024]
    end
  end
end


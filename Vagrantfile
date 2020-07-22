Vagrant.configure '2' do |config|
  config.vm.provider 'virtualbox' do |v|
    v.customize [ 'modifyvm', :id, '--uartmode1', 'disconnected' ]
    v.customize [ 'modifyvm', :id, '--vtxvpid', 'off' ]
    v.memory = 2048
    v.customize ["modifyvm", :id, "--nictype1", "virtio"]
    v.customize ["modifyvm", :id, "--nictype2", "virtio"]
  end
  #config.disksize.size = '100GB' unless ENV['RESIZE'].to_s.empty?
  #config.vm.provision :docker 
  config.vm.box = 'ubuntu/bionic64'
  config.vm.network "forwarded_port", guest: 22, host: 2222, host_ip: "127.0.0.1", id: 'ssh'
  #config.vm.provision(
  #  'shell',
  #  path: 'src/prepare',
  #  privileged: false,
  #  env: {
  #    'BOX_VERSION' => ENV['BOX_VERSION']
  #  }
  #)
  #config.ssh.insert_key = false
  config.vm.network 'private_network', type: 'dhcp'
end

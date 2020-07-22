Vagrant.configure '2' do |config|
  config.vm.provider 'virtualbox' do |v|
    v.customize [ 'modifyvm', :id, '--uartmode1', 'disconnected' ]
    v.customize [ 'modifyvm', :id, '--vtxvpid', 'off' ]
    v.memory = 2048
  end
  #config.disksize.size = '100GB' unless ENV['RESIZE'].to_s.empty?
  #config.vm.provision :docker 
  config.vm.box = 'ubuntu/bionic64'
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

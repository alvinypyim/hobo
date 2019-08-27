Vagrant.configure '2' do |config|
  config.vm.provider 'virtualbox' do |v|
    v.customize [ 'modifyvm', :id, '--uartmode1', 'disconnected' ]
    v.customize [ 'modifyvm', :id, '--vtxvpid', 'off' ]
  end
  config.disksize.size = '100GB' unless ENV['RESIZE'].to_s.empty?
  config.vm.provision :docker 
  config.vm.box = 'ubuntu/bionic64'
  config.vm.provision(
    'shell',
    path: 'src/prepare',
    privileged: false,
    env: {
      'BOX_VERSION' => ENV['BOX_VERSION']
    }
  )
  config.ssh.insert_key = false
end

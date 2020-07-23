Vagrant.configure '2' do |config|
  config.vm.provider 'virtualbox' do |v|
    v.customize [ 'modifyvm', :id, '--vtxvpid', 'off' ]
  end
  unless ENV['RESIZE'].to_s.empty?
    config.vm.disk :disk, size: '100GB', primary: true
  end
  config.vm.provision :docker 
  config.vm.box = 'hashicorp/bionic64'
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

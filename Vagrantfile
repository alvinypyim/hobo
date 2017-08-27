Vagrant.configure '2' do |config|
  config.vm.provider 'virtualbox' do |v|
    v.customize [ 'modifyvm', :id, '--uartmode1', 'disconnected' ]
  end
  config.disksize.size = '100GB'
  config.vm.provision :docker
  config.vm.provision :docker_compose
  config.vm.box = 'ubuntu/xenial64'
  config.vm.provision(
    'shell',
    path: 'src/prepare',
    privileged: false
  )
end

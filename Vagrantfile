Vagrant.configure '2' do |config|
  config.disksize.size = '100GB' unless ENV['RESIZE'].to_s.empty?
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

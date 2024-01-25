# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/jammy64'
  config.vm.box_check_update = false

  config.vm.network 'private_network', type: 'dhcp'

  config.vm.define 'myvm' do |myvm|
    myvm.vm.hostname = 'myvm'
    myvm.vm.provider 'virtualbox' do |vb|
      vb.cpus = 1
      vb.memory = 4096
    end
    myvm.vm.cloud_init :user_data do |cloud_init|
      cloud_init.content_type = 'text/cloud-config'
      cloud_init.path = 'cloud-init.cfg'
    end

    myvm.vm.synced_folder './', '/vagrant'
  end
end

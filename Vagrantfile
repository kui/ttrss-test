# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.hostname = "ttrss-berkshelf"

  config.vm.box = "opscode_ubuntu-12.04"
  config.vm.box_url = 'https://opscode-vm-bento.s3.amazonaws.com/vagrant/opscode_ubuntu-12.04_provisionerless.box'
  config.vm.network :forwarded_port, guest: 80, host: 8080

  # require `vagrant plugin install vagrant-berkshelf`
  config.berkshelf.enabled = true

  # require `vagrant plugin install vagrant-omnibus`
  config.omnibus.chef_version = :latest

  config.vm.provision :chef_solo do |chef|
    chef.json = {
      :mysql => {
        :server_root_password => 'rootpass',
        :server_debian_password => 'debpass',
        :server_repl_password => 'replpass'
      },
      'tt-rss' => {
        'download-url' => 'https://github.com/gothfox/Tiny-Tiny-RSS/archive/1.9.tar.gz'
      }
    }

    chef.run_list = [
        "recipe[ttrss::default]"
    ]
  end
end

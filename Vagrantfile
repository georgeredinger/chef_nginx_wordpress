# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "opscode-ubuntu-12.04-i386"
  config.vm.forward_port 80, 8080
  config.vm.box_url = "~/opscode-ubuntu-12.04-i386.box"
  config.vm.customize ["modifyvm", :id, "--memory", 128]


 config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    #chef.roles_path = "../my-recipes/roles"
    chef.add_recipe "apt"
    chef.add_recipe "openssl"
    chef.add_recipe "ohai"
    chef.add_recipe "runit"
    chef.add_recipe "htop"
    chef.add_recipe "atop"
    chef.add_recipe "build-essential"
    chef.add_recipe "git"
    chef.add_recipe "mysql::server"
    chef.add_recipe "mysql::client"
    chef.add_recipe "nginx"
    chef.add_recipe "php-fpm"
    chef.add_recipe "wordpress"
  # You may also specify custom JSON attributes:
    chef.json = {
      :mysql => {
        :server_root_password => "mysqlRoot",
        :server_repl_password => "mysqlRoot",
        :server_debian_password => "mysqlRoot"
      }
    }
  end
 end


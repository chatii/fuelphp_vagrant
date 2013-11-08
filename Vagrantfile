# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Please change src_dir to project directory name.
  src_dir = "project_name"

  # FuelPHP Staging
  fuel_env = "development"

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise64"
  config.vm.box_url = "http://dl.dropbox.com/u/1537815/precise64.box"
  config.vm.network :private_network, ip: "192.168.33.10"

  doc_root = '/vagrant_data/public'
  
  config.vm.synced_folder src_dir, "/vagrant_data", :create => true, :owner=> 'vagrant', :group=>'www-data', mount_options: ['dmode=775','fmode=775']

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "./cookbooks"
    chef.add_recipe "chatii_fuelphp"
    chef.json = {
      doc_root: doc_root,
      fuel_env: fuel_env
    }
  end
end

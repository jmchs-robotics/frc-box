# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "hashicorp/precise64"

  # Install FRC API and Simulator according to https://wpilib.screenstepslive.com/s/4485/m/23353/l/228979-installing-frcsim-with-a-terminal
  config.vm.provision "shell", path: 'http://first.wpi.edu/FRC/roborio/release/frcsim-installer.sh', args: 'INSTALLER'
end

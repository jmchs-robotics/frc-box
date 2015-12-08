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
  config.vm.box = "box-cutter/ubuntu1404-desktop"

  # Disable VirtualBox GUI from opening by default.
  # You can tell Vagrant to open the GUI, or use X-Server tunneling over SSH.
  config.vm.provider "virtualbox" do |v|
    v.gui = false
  end

  # The default base box does not support HyperV, we override a box that will.
  config.vm.provider "hyperv" do |v, override|
    override.vm.box = "withinboredom/Trusty64"
  end

  # Create a chain of priority for providers.
  config.vm.provider "hyperv" # Prefer HyperV, this will only be avalible on Windows.
  config.vm.provider "vmware_fusion" # Use VMWare if installed, HashiCorp maintains an offical plugin for VMWare.
  config.vm.provider "vmware_workstation" # Ditto.
  config.vm.provider "parallels" # Prefer Parallels if installed.
  config.vm.provider "virtualbox" # Use VirtualBox if nothing else is set up.

  # Install FRC API and Simulator according to https://wpilib.screenstepslive.com/s/4485/m/23353/l/228979-installing-frcsim-with-a-terminal
  config.vm.provision "shell", path: 'http://first.wpi.edu/FRC/roborio/release/frcsim-installer.sh', args: 'INSTALLER'

  config.push.define "atlas" do |push|
    push.app = "kepler/frc"
    push.vcs = true
  end
end

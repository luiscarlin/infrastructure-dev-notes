# Vagrant Commands

```bash
# start a new vagrantfile and use precise64 box
vagrant init hashicorp/precise64

# start the VM. No UIs.
vagrant up

# ssh into the VM
vagrant ssh

# kill the VM
vagrant destroy

# create a new project
vagrant init

# base images = boxes
# download a box for all vagrant projects to use
# from https://atlas.hashicorp.com/boxes/search
# you can also write your own
vagrant box add hashicorp/precise64

# set box to use
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  # (optional) config.vm.box_version = "1.1.0"
  # (optional) config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  # (optional - use the shell provisioner) config.vm.provision :shell, path: "bootstrap.sh
  # (optional - port forwarding) config.vm.network :forwarded_port, guest: 80, host: 8080
end

# remove the box
vagrant box remove

# reload the VM and run provisioners (shell, etc)
vagrant reload --provision

# reload the VM (without running provisioners). 
# use when editing vagrantfile and just restarting
vagrant reload

# generate a unique url for your running VM accesible to the public
vagrant login
vagrant share

# save current state and stop
# uses lots of disk space to suspend
vagrant suspend

# safely powers down machine
# takes some time to stop and start up
# will take some space
vagrant halt

# stops and destroys the VM
# all resources re-claimed
vagrant destroy


# if using vbox, you can list all the VMs
vboxmanage list vms
```

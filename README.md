# test-vm-with-vagrant

### 0. Setup VM with Vagrant
Download Virtualbox from
[Installer](https://www.virtualbox.org/wiki/Downloads)

For macOS (with homebrew)
```sh
brew tap hashicorp/tap
brew install hashicorp/tap/hashicorp-vagrant
```
Check if install
```sh
vagrant --help
```
Add box(image/OS), _**can't use ubuntu/jammy64 due to it's suitable for Intel/AMD not M-series chip**_
```sh
vagrant init bento/ubuntu-22.04
```
Run vm
```sh
vagrant up
```
Check box
```sh
vagrant box list       
```
Check status
```sh
vagrant status      
```
Check status in detail
```sh
vagrant global-status      
```
Stop vm
```sh
vagrant halt   
```
Restart vm
```sh
vagrant reload   
```
Access vm
```sh
vagrant ssh   
```
Logout from vm
```sh
crtl+d 
```


### 1. Mount disk
Set in Vagrantfile, for example
```vagrantfile
Vagrant.configure("2") do |config|
  config.vm.disk :disk, name: "backup", size: "5GB"
  config.vm.disk :floppy, name: "cool_files"
end
```
_PS. found issue can't add floppy type_

After config, use command
```sh
vagrant up
```
Check disk size
```sh
lsblk
```
Note: Can't shrink size directly, need to remove before set new disk size

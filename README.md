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
Add box(vm), _**can't use ubuntu/jammy64 due to it's suitable for Intel/AMD not M-series chip**_
```sh
vagrant init bento/ubuntu-22.04
```
Run box
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
Access vm
```sh
vagrant ssh   
```
Logout from vm
```sh
crtl+d 
```
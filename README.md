![Header](https://i.imgur.com/tE6Wfee.png)

# Ansible + Vagrant + Virtualbox

### Laravel Vagrant machine
* Ubuntu Bionic
* Nginx Latest
* Redis Latest
* MySQL 8.0
* PHP 7.3
* Composer

### Install
1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](https://www.vagrantup.com/)
2. Clone project
3. `cd dev-vm`
4. Run `vagrant up`

### Configure
MySQL users and databases
* Edit: `roles/mysql/vars/main.yml`

PHP version
* Edit: `roles/php/defaults/main.yml`

Path to project
* Edit: `Vagrantfile` (`config.vm.synced_folder`)



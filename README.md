# vagrant-lamp-sf2

A super-simple `Vagrantfile` and `bootstrap.sh` to setup a LAMP stack inside Vagrant 100% automatically.

Designed to work well with Symfony 2 framework.

If you want simple and universal LAMP use https://github.com/panique/vagrant-lamp-bootstrap instead.

### What's inside ?

This is a reduced-to-the-max Vagrant setup file for a quick development stack. It will:

* setup a Ubuntu 14.04 LTS "Trustry Thar" 64bit box
 
* run `nfs` sync mode

* sync the current folder with `/var/www/html/vagrant` inside the box

* automatically perform all the commands in `bootstrap.sh` directly after setting up the box for the first time

The bootstrap.sh will:

* update, upgrade

* create a folder inside `/var/www/html`

* install apache 2.4, php 5.5, MySQL, PHPMyAdmin, git and Composer

* install `php5-intl`, `mcrypt`

* also setting a pre-chosen password for MySQL and PHPMyAdmin

* activate mod_rewrite and add Symfony 2 recommended and optimized vhost

Password is set to `symfony` but you can change it in `bootstrap.sh` for sure.

### How to use ?

Install vagrant plugin `vagrant-winnfsd` if using Windows host and restart machine.

Put `Vagrantfile` and `bootstrap.sh` inside a folder and do a `vagrant up` on the command line.
This box uses Ubuntu 14.04 LTS "Trustry Thar" 64bit, so if you don't have the basic box already, do a 
`vagrant box add ubuntu/trusty64` before.

# PCSETUP

## Usage

### Pre-requisites

* An Arch Linux installation with internet access
* Create an user with the name you desires using `useradd <NAME> -m`
* Add this user to the sudoers list

### First time only

* At the root dir run `make preconfig`
  - Creates `sudo` group and add the current user to it as several ansible steps will require sudo
  - Create a super user that can run sudo passwordless. This is require to properly make pacaur work without asking sudo password
  - Update the system
  - Install ansible
* If you are not me, you need to [set your own personal information](https://github.com/rafamanzo/pcsetup/wiki/Replace-my-personal-information-by-yours)
  - Specially set the vault files and password

### Everyday

* `ansible-playbook <HOST PLAYBOOK> -K`

## Known ~~issues~~ features

### Firewall (UFW)

* Locks you out of Vagrant box after rebooting the machine
  - Going through the VirtualBox's gui, disable UFW (`sudo ufw disable`) and reload the box (`vagrant reload`)
* CUPS network printer discovery
  - Simplest thing is to disable UFW while setting up the printer (`sudo ufw disable`), set it up and enable UFW back (`sudo ufw enable`). After configured the printer should stay working
  - If you know the printer network address and model (for driver choosing), you can go through CUPS configuration process

## Managed machines

* BURN-E (Notebook)
  - Specs
    * Intel Core i7 2620M
    * Geforce GT 520M
    * 8 GB RAM
    * 240 GB SSD
    * 640 GB HDD
  - Statistics (v1.0.0)
    * Boot time: < 20s
    * Mem. usage after boot: ~190MB
    * Expected battery life: ~3h
    * Disk usage: 8.6GB
* WALL-A (Desktop)
  - Specs
    * AMD FX8320E
    * Geforce GTX 1050
    * 16 GB RAM
    * 256 GB SSD
    * 300 GB HDD
    * 1 TB RAID1 HDD
  - Statistics (v1.6.1)
    * Boot time: < 23s
    * Mem. usage after boot: ~260MB
    * Disk usage: 11.5GB

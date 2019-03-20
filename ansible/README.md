# Ansible playbooks

This are the ansible playbooks to provision the nodes of my Docker Swarm cluster running on Armbian Stretch over several ODROID C2's.

## Usage

Update the `inventory` file to reflect your hosts. Then you can apply the playbooks to your inventory with the command:

`$ ansible-playbook -i inventory -u root -k ./cluster.yml`

**Please note this requires an Ansible version >= 2.8**

## Hardware

* Platform: ODROID C2
* CPU: ARM Cortex-A53 @ 1.5Ghz
* RAM: 2GB DDR3 SDRAM

##### Master node

* Charles

##### Worker nodes

* Linda
* Lynette

## Flashing Commands

I am using the stable Stretch version of [Armbian](https://www.armbian.com/odroid-c2/).

```bash
$ diskutil list
$ sudo diskutil unmount /dev/disk3s1
$ sudo dd bs=1m if=Armbian_5.59_Odroidc2_Debian_stretch_next_4.18.8.img of=/dev/rdisk3
```

## Todo

* set nameservers? - fix 120.0.0.53 bullshit
* delete odroid user?
* docker system prune cronjob
* do we need to disable swap? - /etc/default/armbian-zram-config
* can we automate headless odroid boot mode?

## Development

You can bring up Vagrant machines to test ansible locally.

`$ vagrant up`

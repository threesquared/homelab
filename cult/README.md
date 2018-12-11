# ODROID C2 Docker Swarm

This is the Ansible playbook and docker swarm config files for my services cluster running on
Armbian Stretch on several ODROID C2's.

## Usage

Update the `inventory` file to reflect your hosts. Then you can apply the playbooks to your inventory with the command:

`$ ansible-playbook -i inventory -u root -k ./ansible/cluster.yml`

**Please note this requires an Ansible version >= 2.8**

## Flashing Commands

I am using the stable Stretch version of [Armbian](https://www.armbian.com/odroid-c2/).

```bash
$ diskutil list
$ sudo diskutil unmount /dev/disk3s1
$ sudo dd bs=1m if=Armbian_5.59_Odroidc2_Debian_stretch_next_4.18.8.img of=/dev/rdisk3
```

## Services

* InfluxDB - Metric database
* Telegraf - Metric collector
* Grafana - Visualise metrics
* MariaDB - Database for Kodi
* Kodi - Headless Kodi for media library updates
* Resilio - Phone media backups
* Transmission - Torrent downloads
* CouchPotato - Movie download management
* SiCKRAGE - TV download management
* Logstash - Collect logs from pfSense

## Development

You can bring up Vagrant machines to test ansible locally.

`$ cd ansible && vagrant up`

## Hardware

* Platform: ODROID C2
* CPU: ARM Cortex-A53 @ 1.5Ghz
* RAM: 2GB DDR3 SDRAM

##### Master node
* Charles

##### Worker nodes
* Linda

## Todo

* set nameservers? - fix 120.0.0.53 bullshit
* delete odroid user?
* docker system prune cronjob
* disable swap? - /etc/default/armbian-zram-config

## Misc Resources

* https://github.com/mrlesmithjr/ansible-rpi-k8s-cluster/blob/master/playbooks/bootstrap.yml
* https://github.com/Project31/ansible-kubernetes-openshift-pi3/blob/master/roles/kubernetes/tasks/apt.yml
* https://github.com/rak8s/rak8s/blob/master/roles/kubeadm/tasks/main.yml
* https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-1-10-cluster-using-kubeadm-on-ubuntu-16-04
* http://michele.sciabarra.com/2018/02/12/devops/Kubernetes-with-KubeAdm-Ansible-Vagrant/
* https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/
* https://vadosware.io/post/hetzner-fresh-ubuntu-install-to-single-node-kubernetes-cluster-with-ansible/
* https://github.com/geerlingguy/ansible-role-kubernetes
* https://medium.com/@evnsio/managing-my-home-with-kubernetes-traefik-and-raspberry-pis-d0330effea9a
* https://github.com/hypriot/blog/blob/master/content/post/setup-kubernetes-raspberry-pi-cluster.md
* https://medium.com/@joatmon08/playing-with-kubeadm-in-vagrant-machines-part-2-bac431095706

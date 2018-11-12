# ODROID C2 Kubernetes Cluster

This is the Ansible playbook and Kubernetes config files for my Kubernetes cluster
on several ODROID C2's running Armbian Stretch.

## Usage

You can apply the playbooks to your inventory with the command:

`$ ansible-playbook -i inventory -u root -k cluster.yml`

## Pods

* [Traefik](./kubernetes/traefik) - Ingress Controller
* InfluxDB - Metric database
* Telegraf - Metric collector
* Grafana - Visualise metrics
* MariaDB - Database for Kodi
* Kodi - Headless Kodi for media library updates
* Resilio - Phone media backups
* Transmission - Torrent downloads
* [CouchPotato](./kubernetes/couchpotato) - Movie download management
* SiCKRAGE - TV download management
* Logstash - Collect logs from pfSense

## Hardware

* Platform: ODROID C2
* CPU: ARM Cortex-A53 @ 1.5Ghz
* RAM: 2GB DDR3 SDRAM

##### Master node
* Charles

##### Worker nodes
* Linda

## Development

You can bring up two Vagrant machines to test locally.

`$ vagrant up`

## Todo

* set nameservers? - fix 120.0.0.53 bullshit
* delete odroid user?
* docker system prune cronjob
* remove ExecStartPre line from containerd?
* reboot after dist upgrade to modprobe?
* disable swap - /etc/default/armbian-zram-config

## Resources

Various links

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

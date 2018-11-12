# Homelab
This repository contains config files for my various homelab servers.

## Diagram

This is a digram of the network.

![Diagram](diagram/diagram.png)

## Cult

This contains Ansible and Kubernetes configs for the ODROID C2 kubernetes cluster.

[Link](./cult)

## Trap House

This contains docker-compose config for the Raspberry Pi Cowrie SSH honeypot.

[Link](./trap-house)

## Blackstar

This contains an encrypted config for my pfSense firewall.

[Link](./blackstar)

# Resources

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

# Notes

* ansible-playbook -i inventory -u root -k cluster.yml
* set nameservers - fix 120.0.0.53 bullshit
* delete odroid user?
* docker system prune?
* remove ExecStartPre line from containerd?
* reboot after dist upgrade to modprobe
* disable swap - /etc/default/armbian-zram-config

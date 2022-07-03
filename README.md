# pi-ansible
## Setup `ansible` User
```bash
useradd -mU ansible
usermod -aG sudo ansible
mkdir /home/ansible/.ssh
chmod 700 /home/ansible/.ssh
echo '# SSH keys go here' >> /home/ansible/.ssh/authorized_keys
chmod 600 /home/ansible/.ssh/authorized_keys
chown -R ansible:ansible /home/ansible/.ssh
echo "ansible ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
```

## (Optional) SSH-Key for root
```bash
mkdir /root/.ssh
chmod 700 /root/.ssh
echo '# SSH keys go here' >> /root/.ssh/authorized_keys
chmod 600 /root/.ssh/authorized_keys
```

# Use K3s Cluster Playbook
Deployment environment must have Ansible 2.4.0+
Master and nodes must have passwordless SSH access

1. create `inventory/pi-cluster.ini` containing master and node hosts. For example:
```bash
[master]
192.168.0.10

[node]
192.168.0.[11:12]

[k3s_cluster:children]
master
node
```

2. edit `k3s-cluster/group_vars/all.yml` to change cluster variables

3. run playbook
```bash
ansible-playbook k3s-cluster/site.yml -i inventory/pi-cluster.ini
```

4. copy cluster config to get access
```bash
scp ansible@master_ip:~/.kube/config ~/.kube/config
```
# Ansible Playbook for RKE2
Minimal playbook for RKE2 installation that uses [lablabs/ansible-rke2-role](https://github.com/lablabs/ansible-role-rke2)

## Usage
- Install the required role by running `ansible-galaxy install lablabs.rke2`
- Edit the _inventory_ file with the correct number of **masters** and **workers**
- Edit the _vars/main.yml_ file:
  - *rke2\_api\_ip* -> enter the load balancer address if you want to run in HA mode
  - master*_ip / worker*_ip -> enter the IP addresses of your machines
  - *ssh\_key\_path* -> enter the path to your SSH key
- Edit the _playbooks/rke2-playbook.yml_:
  - Set the **rke2\_ha\_mode** variable
  - If you want to set your own token edit the *rke2\_token* variable

Run the following command: `ansible-playbook playbooks/rke2-playbook.yml -i inventory`

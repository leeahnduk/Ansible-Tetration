# Ansible Tetration Sensors
This application helps to quickly deploy deploy Tetration sensors and create key for a Ubuntu K8s Cluster automatically.

## Table of contents
* [Installation](#Installation)
* [Screenshots](#screenshots)
* [How to Use](#UserGuide)
* [Steps to run](#Steps)
* [Feedback and Author](#Feedback)

## Installation

From sources

Download the sources from [Github](https://github.com/leeahnduk/Ansible-Tetration.git), extract and execute the following commands

```
$ git clone https://github.com/leeahnduk/Ansible-Tetration.git

```

## Screenshots
![Run screenshot](https://github.com/leeahnduk/Ansible-Tetration/blob/master/Ubuntu/Ansible-Ubuntu.jpg)
![Result screenshot](https://github.com/leeahnduk/Ansible-Tetration/blob/master/Ubuntu/Result.jpg)
![Tetration screenshot](https://github.com/leeahnduk/Ansible-Tetration/blob/master/Ubuntu/Tetration.jpg)

## UserGuide
How to use this application:
* You need to have an ansible VM to run Ansible Playbook. It can run on CentOS or Ubuntu VM. How to setup, please use this link: https://www.ansible.com/resources/videos/quick-start-video?extIdCarryOver=true&sc_cid=701f2000001OH7YAAW
* Copy ssh public key of ansible machine to K8s Master and Workers Nodes.
* Run in ansible VM: eval `ssh-agent -s, ssh-add ~/.ssh/id_rsa, ssh-keygen -R Remote_VMs_IP`
* export ANSIBLE_HOST_KEY_CHECKING=False in ansible VM
* Edit to match with the destination environment (vCenter, Portgroups, VM Folder, DC, …) in Group_vars, Hosts folders.
* can ssh to the remote K8s VMs to test: ssh ubuntu@…, sudo -i, yum install -y ...
* Download Ubuntu Sensors rpm file and host in Web server. Change the ansible playbook to match with your web server. 
* to run ansible playbook, use command:  `ansible-playbook -i hosts/ubuntu tet_install_k8s.yml`


## Steps

Step 1: Issue `git clone https://github.com/leeahnduk/Ansible-Tetration.git` to install.

Step 2: Modify all the above parameters to match with your environment.

Step 3: Run the apps: `ansible-playbook -i hosts/ubuntu tet_install_k8s.yml`


## Feedback
Any feedback can send to me: Le Anh Duc (leeahnduk@yahoo.com or anhdle@cisco.com)

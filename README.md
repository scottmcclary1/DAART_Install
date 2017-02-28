# DAART Installation

Guide to install DAART and its dependencies.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### First time only 

What things you need to install the software and how to install them

Load Python Module
```
module load python/2.7.3
```

Create Virtual Environment
```
virtualenv ~/.venv
```

Activate Virtual Environment
```
source ~/.venv/bin/active
```

Install Ansible
```
pip install ansible
```

### Every other time

Using the software after its been installed

Activate Virtual Environment
```
source ~/.venv/bin/active
```

Ensure hosts file is accurate
```
cat hosts/hosts 

[local]
localhost ansible_connection=local ansible_user=scmcclar

[remote]

karst.uits.iu.edu ansible_user=scmcclar
bigred2.uits.iu.edu ansible_user=scmcclar

[karst]

karst.uits.iu.edu ansible_user=scmcclar

[kd-beta]

i1.karst.uits.iu.edu ansible_user=scmcclar
i2.karst.uits.iu.edu ansible_user=scmcclar
i3.karst.uits.iu.edu ansible_user=scmcclar
i4.karst.uits.iu.edu ansible_user=scmcclar
i5.karst.uits.iu.edu ansible_user=scmcclar
i6.karst.uits.iu.edu ansible_user=scmcclar
i7.karst.uits.iu.edu ansible_user=scmcclar
hm008.karst.uits.iu.edu ansible_user=scmcclar
hm009.karst.uits.iu.edu ansible_user=scmcclar
hm011.karst.uits.iu.edu ansible_user=scmcclar
hm012.karst.uits.iu.edu ansible_user=scmcclar
hm013.karst.uits.iu.edu ansible_user=scmcclar
hm014.karst.uits.iu.edu ansible_user=scmcclar
hm015.karst.uits.iu.edu ansible_user=scmcclar
hm016.karst.uits.iu.edu ansible_user=scmcclar
```

Make sure you are aware of where Node-Webkit and DAART will be installed
```
cat vars/daart
---
# Variables here are for daart

daart_path: ~/DAART
node_webkit_path: /tmp
```

Install Node-Webkit
```
ansible-playbook -i hosts/hosts install_node_webkit.yml
```

Install DAART
```
ansible-playbook -i hosts/hosts install_daart.yml
```

### Uninstall Node-Webkit and DAART (rarely needed)
Install Node-Webkit
```
ansible-playbook -i hosts/hosts uninstall_node_webkit.yml
```

Install DAART
```
ansible-playbook -i hosts/hosts uninstall_daart.yml
```


## Authors

* **Scott McClary** 

## Acknowledgments

* SciAPT
* SCA

# DAART Installation

Guide to install DAART and its software dependencies (Node-Webkit) on Karst Desktop Beta. 

## Configure Environment on Karst 

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

## Install on Karst 

Using the software after its been installed

Activate Virtual Environment
```
source ~/.venv/bin/active
```

Ensure hosts file is accurate
```
cat hosts/hosts 

[karst]

karst.uits.iu.edu 

[kd-beta]

i1.karst.uits.iu.edu 
i2.karst.uits.iu.edu 
i3.karst.uits.iu.edu 
i4.karst.uits.iu.edu 
i5.karst.uits.iu.edu 
i6.karst.uits.iu.edu 
i7.karst.uits.iu.edu 
hm008.karst.uits.iu.edu 
hm009.karst.uits.iu.edu 
hm011.karst.uits.iu.edu 
hm012.karst.uits.iu.edu 
hm013.karst.uits.iu.edu 
hm014.karst.uits.iu.edu 
hm015.karst.uits.iu.edu 
hm016.karst.uits.iu.edu 
```

Ensure vars are accurate for installation
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

## Uninstall Node-Webkit and DAART
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

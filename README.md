# prerequisites

- installed vagrant
- installed virtualbox
- installed git
- cloned this repository.

## add boxes
    vagrant box add rockylinux/9 #(! this one is with arm64 support @macbook users!) 
    vagrant box add maxhamon/debian12
    vagrant box list
## vagrant up
    vagrant up --provider virtualbox

### inventory
will be located at '.vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory' after succesfully provisioning.  
this inventory can be used by ansible-playbook:

    ansible-playbook -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory playbook.yml 

These paths can be relative, so -i ../../.vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory would also work, if for example, you wanted to create a 
# lab
configure two web servers located in different regions. 

|server   |web1   |web2   |
|---|---|---|
|region   |AM3   |FS1   |
|country   |NL   |DE   |

## beginner
Create a role that installs the webserver of your choice on both machines.

hint: ansible-galaxy role init 

## advanced
Change the created role (or create a new one) to include different web pages (Dutch or German) depending on what region the host is located in.  

hint: try using jinja templating for templating different languages.


### solutions/examples

the examples/ folder contains some (really quickly made, not complete) examples for how I would start when creating certain roles. THERE IS NO "RIGHT" WAY! if it works it works. I highly encourage you to read the documentation and to try and come up with your own solutions  

### possibly related documentation

 - https://docs.ansible.com/ansible/latest/collections/ansible/builtin/package_module.html
 - https://docs.ansible.com/ansible/latest/collections/ansible/builtin/copy_module.html
 - https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html
 - https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html
 - https://docs.ansible.com/ansible/latest/collections/ansible/builtin/lineinfile_module.html
 - https://docs.ansible.com/ansible/latest/collections/ansible/builtin/blockinfile_module.html
 - https://docs.ansible.com/ansible/latest/collections/ansible/builtin/stat_module.html
 - https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_templating.html

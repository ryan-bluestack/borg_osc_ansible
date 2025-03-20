# init 
    vagrant init
    
## add boxes
    vagrant box add ssplatt/rocky9
    vagrant box add maxhamon/debian12
    vagrant box list
## vagrant up
    vagrant up --provider virtualbox

### inventory
will be located at '.vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory' after succesfully provisioning
this inventory can be used by ansible-playbook:

    ansible-playbook -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory playbook.yml 

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

hint: try using jinja templating

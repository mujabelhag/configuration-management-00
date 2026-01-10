- Ansible Architecure 
- Ansible Components
- Modules, Tasks, And Playbooks 

# Ansible Architecure :

Agentless:
we mean by agentless there is no need to run or install a software on the managed resource 

why does agentless matters is because :
- no agent setup or maintain
- simpler and secure 
- quicker host onboarding
- easier troubleshooting 

# How ansible works :
- connecting via ssh (ansible use ssh to connect with the managing resources)
- copy python modules (a python modules copied to the managed node)
- tasks execution 
- clean up 

# key characteristcis of ansible :
- agentless
- yml playbooks 
- push-based(control/master node push the configs when it's needed)
- idempotent(everytime we apply the config it will not result in the system  already configured)

# Real-wold agentless architecture:
- cloud provisioning 
- infrastructure audits
- cross-platform deployments
- temporary instances

# Ansible Components:
ansible having three main components:
- control/master node
- managed node 
- inventory file 

# control/master node :
it is the system where the ansible is setup in most of the cases it is our local machines
it runs ansible , handle the playbooks , and needs ssh access

# managed node :
it is the remote resources that we want to configure (servers/ db/ containers )
it is what we need to configure and it needs ssh access and python installed 
# inventory file :
the file that contains the details of all the resources 
and it is .ini format that contains all the resources details 


# Ansible file components :
- mosules : are a reusable functions used to do a specific action (yum,apt,copy,file,user,pin,command,shell service )
- tasks : it a single unit of work calling a module 
- playbooks it is a structured .yml file that is defining a complete automation task

# some ansible commands:
ansible  <host-group> -i inventory -m <module> -a<arguments>
ansible all -i inventory.ini -m ping (to test the conectivity)
ansible all -i inventory.ini -m setup 
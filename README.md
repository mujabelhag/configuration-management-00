## CONFIGURATION MANAGEMENT:

- Undrestanding the configuration management .
- Deep dive into configuration drift 
- Popular configuration management tools
- Setting up ansible tool 


# Undrestanding Configuration Management:

before devops and sysadmins devs used to do the work manually starting from 
- sshing to the servers 
- installing the dependencies for each server 
- configure each server (by editing .config files)
-  copying scripts
all this maunall work result some problems sush as :
- human errors
- inconsistency for our system 
- time consuming 
- versioning cotrol (we will not be having the concept of who did what )


so instead of doing all this manuall work .configuration managements comes to the picture
to reduce this manuall work and human .

# configuration management : 
it is the process of handling the changes systematically to ensure system integrity .
it helped us in :
- system consistency
- testability 
- version control 
- disaster recovery 
- idempotency (and it is the ability to reapplying the configuratuon without doing any changes to the system )

# CONFIGURATION DRIFT :
it's the procees of when the actuall state and the desired state are not the same 
for example :
desired state: install and run nginx 
actuall stats: someone has deleted nginx 

# configuration drift usually comes from :
- manuall hotfixes (making changes under pressure from production level environment)
- untracked changes 
- different patch levels

# POPULAR CONFIGURATION MANAGEMENT TOOLS :
- Ansible (Agentless, .ini or .yml , )
- Puppet (Agent-base, puppet Dsl , for large interprise)
- Chef (Agent-base , Ruby  )

Ansible is the most preferable tool because it,s simple and readable in .yml format 

configuration management tools helps in :
- detect and fix the drift by inforcing a known configurations 
- apply the changes useing declarave model (all we have to do is just tell the tool what's need to be done ..not step by step procedure)
- uses inventory files to track the system state


# Quick Comparison Between Declarative And Procedural Models :

# procedural model :
is a step by step instructions 
example :
if we want to install nginx in a specific resource / server  we run the following
sudo apt update 
sudo apt upgrade -y 
sudo apt install nginx -y 

# declaraive model :
it is like we just tell the system what we want 
example:
- name: install nginx
  hosts: all 
  become: yes 

  tasks:
    - name: install nginx
      apt:
      name: nginx
      state: present

this how we differentiate between the declarative and procedural approachs



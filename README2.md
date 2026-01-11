# Ansible inventory file types :
there are two types for ansible inventory file 
- static inventory file 
- dynamic inventory file 

# Static inventory file :
it's the normal inventory file that we have used earlier  to group our resources and dbs 
the problem with this static inventory file is .. when we use it on  large projects which contains a huge number of resources and for some reasons a lot of them has been crashed so it's difficult to manage all of them in the inventory file 
this static inventoy file is suitable for small projects that is having a small number of resources ..so that we can manage them easily

example for this static inventory file is the file (inventory.ini in this repo )


# Dynamic inventory file :

in this file ansible ask for a provider in order to reach to the instance by getting it's details such as ips 
and it uses the concept of the plugins 

# Plugins :
it acts as a bridge between ansible and the provider to get the details of the instance 

in a simple and short notice ...
static inventory file is like a prented guest list for party 
dynamic inventory file is like live google sheet having updated list ..even if anyone comes at the last time ..he will be included.

# plugins :
- aws_ec2.yml
- gcp.yml
- azure-rm.yml


# Essential ansible modules:
- file management: (file,copy)
- package management: (yum,apt)
- service control: (service, systemctl)
- shell and user management: (shell,command,user,groups)

# Handlers in ansible :
handlers are a special tasks in ansible triggerd by notifications 
like for example :
if the task has been changed it will notify the handler , if the task doesn't change that is idempotent and the 
handler will not be triggerd 


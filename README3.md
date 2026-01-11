# Ansible Roles :
when we have a playbook and as it becomes so large due to adding multiple tasks in the playbook
and it may become so tough to be undrestandable ..here the roles comes up 

# Roles :
it a way that breaks a large playbook into a reusable components making our playbook easier to read 
and undrestand 

it's going to 
- break larger playbook 
- structure organisation
- improve scalability 


# Roles structure :


roles/
└── nginx/
    ├── tasks/
    │   └── main.yml
    ├── handlers/
    │   └── main.yml
    ├── templates/
    │   └── nginx.conf.j2
    ├── files/
    │   └── index.html
    ├── vars/
    │   └── main.yml
    ├── defaults/
    │   └── main.yml
    ├── meta/
    │   └── main.yml

    the role name is nginx and inside this role are the files that ansible will go through 

- example for role 

- hosts: all
  become: yes 
  roles:
    - nginx  


# Ansible-galaxy :
ansible galaxy is an official hub for sharing and reusing ansible contents,it is like for creating 
roles and collections like modules 

for example if we need to create a role we use the following command:
ansible-galaxy init nginx_setup 
the above command is going to create a role with it's file ready .

# jinja2 templetes:
they are a templet engines that are going to injects the variables inot files at the runtime 
and we save it's file as .j2 
example:
<head><title>welcome{{website_name}}</title></head>  (config.j2)
from the vars file it will look for the {{wesite_name}} and injects it to the file 

# Ansible Vaults: securing secrets :
it is a mechanism that help us to encrypt our information .
it help us to securly encrypt our data in a secret file, so that no one can reach it and perform tasks.

for example: 
i have created a file called secrets.yml and it is having a sensetive information about me 
i used the comaand 
ansible-vault encrypt secrets.yml (the file has been encrepted after setting a vault pass)
and if we need to decrypt it 
we use the same command but replace decrypt interms of encrypt .


# Error handling in ansible:

we use the two command for error handling:
- ignore-errors : it is used like to continuou despite if there is errors 
ignore-errors: yes 

- fialed_when:

- name: check disk usage 
  command: df -h/
  register: disk_output
  failed-when: "100% in disk_output.stdout"

  # debugging in ansible :
  the following commands are for debugging in ansible:
  - --check : it is for dry run like running it will nt apply what happens ,we use it to just see what will happen and it is zero effects on the prod 

  - ansible-palybook --check playbook.yml


  - verbosity: and it gives us a detailed output 
  ansible-playbook playbook.yml -v 
  ansible-playbook playbook.yml -vv 
  ansible-playbook playbook.yml -vvv


  1. What is the difference between a static inventory file and a dynamic
inventory, and when would you prefer dynamic inventory?
2. What is a handler in Ansible, and how is it different from a normal task?
3. What problem do Ansible roles solve, and name at least three standard
directories inside a role.
4. Why is Ansible Vault used, and name one command to encrypt an existing
variables file.
5. Explain the purpose of ignore_errors, failed_when, and one module or flag
commonly used for debugging playbooks.
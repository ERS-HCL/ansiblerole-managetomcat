# ansible_role_manage_tomcat

# Description:

	This Tomcat Ansible role can be used for performing common administrative tasks for managing tomcat in local and remote machines.
	This Ansible role has the support tasks like install, uninstall, setup tomcat configuration, users, Shutdown, start, taking backup of tomcat, deployment of application.

# Requirements:
Before installing tomcat, we need to install java and setup env variables JAVA_HOME.
JDK 1.8
ansible, ansible-galaxy installed. 

# Execution:
Local:
	To install tomcat into local machine, upate manage_tomcat.yml file, as given below.
---
- hosts: hosts
  connection: local
#  remote_user: root
# become: yes

To run this playbook for local machine use below command:
ansible-playbook manage_tomcat.yml

Remote:
	If you want install into remote machine , update manage_tomcat.yml file , as given below:
---
- hosts: hosts
#  connection: local
  remote_user: root
  become: yes

To run this playbook for remote machine use below command:
ansible-playbook -i inventory/hosts manage_tomcat.yml

# To verify tomcat installation
	open any browser and give http://<ip>:8080 (default port number 8080) and hit enter, to see the default tomcat page.


# Sample execution command with choice

	Use below command, to execute playbook with choice of tomcat tasks to perform. If no choice is given, user will be prompted to enter the choice.

        ansible-playbook -i inventory/hosts manage_tomcat.yml –e choice=01


# Application Deployment:
	Update the war file path in main.yml in roles\deployment directory(/roles/deployment/tasks/main.yml }, before executing this role.
        This can be customised to take user inputs and passed to roles based on the task choices.




 
 
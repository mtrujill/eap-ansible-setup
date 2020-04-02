# eap-ansible-setup

This ansible playbook was written to give a demo to a customer on how to automate the installation and configuration of JBoss EAP using ansible.

## Setup

Two CentOS virtual machines were created on a laptop. One was used as the Ansible master node and the other was used to host the EAP installation. The playbook performs the following tasks:

1. Unzips the JBoss EAP zip file on the Ansible master onto the EAP host machine. It then changes the permissions of the EAP install.
2. The $EAP_HOME/bin/add-user.sh script is executed to create an EAP management and application user.
3. Configures JBoss EAP to run as a service to use systemctl to start JBoss EAP on machine startup. 
4. Configures the JBoss EAP public, secure, and unsecure interfaces to accept all clients.
5. Installs Maven and Git on the EAP host machine.
6. Creates a developer sandbox to clone the EAP quickstarts from GitHub.
7. Clones the quickstarts to the sandbox and builds the helloworld application.
8. Deploys the helloworld applciation to the EAP service. 

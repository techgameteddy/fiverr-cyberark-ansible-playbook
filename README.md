# CyberArk CRUD Playbook
This playbook is used to create, remove, update/rotate api keys, and delete
user account connected to a Cyber Ark system.


## Important Variables

Reference the following environment variables within your Ansible Playbook when using this Credential Type:

* `CYBERARK_API_URL` \
This is the Base URI of your CyberArk Password Vault Web Access (PVWA). _e.g. `https://pvwa.cyberark.com`_

* `CYBERARK_API_USERNAME` \
This is the username to use when logging into the CyberArk PAS Web Services SDK (REST API).

* `CYBERARK_API_PASSWORD` \
This is the password associated with the username provided for login.

* CYBERARK_AUTH_USERNAME: 'testaccount1'
This is the username to be manipulated by the playbook

* CYBERARK_AUTH_PASSWORD: 'password1'
This is the given password for the account being manipulated by the playbook

* CYBERARK_AUTH_EMAIL: 'ansibleuser@demo.com'
This is used for provisioning or deprovisioning use accounts

* CYBERARK_AUTH_INTIT_PW: "password1"
This is used of provisioning new accounts or resetting passwords


## Tests Demos
This playbook is task specifc, to run the tasks with out Ansible Tower you
can do the following:

 example playbook dir: /home/user/ansible/crud-playbook

$ cd /home/user/ansible

$ ansible-playbook -i /path/to/inventory/file -l <cyberark_hostname> crud-playbook.tasks/main.yml
 (you can change the main.yml to any other tasks to specify the job requested. For creating a new user you can change this command to use provision_user.yml at the end instead of main.yml )



note: change variables in the defaults/main.yml file before running any specific tasks.



main.yml - Test connection to CyberArk Api Server
changepolicy.yml - Change Policy in CyberArk  
deprovision_account.yml - Remove a CyberArk Account
deprovision_user.yml - Removing a CyberArk User
disable_user.yml - Disabling a CyberArk User
enable_user.yml - Enabling a CyberArk User
provision_account.yml - Create CyberArk user account with preset variables
provision_user.yml - Creating a CyberArk User
reset_user_password.yml - Enabling a CyberArk User and forcing a password change at next logon
test.yml - connect to cyberark api and check for admin account

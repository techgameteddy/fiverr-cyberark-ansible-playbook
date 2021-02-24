# CyberArk PAS REST API

Custom Credential Type for Ansible Tower

## Installation

1. Login to Ansible Tower as a Tower Administrator.
2. Under Administration, click on Credential Type.
3. Click the green [ + ] in the top right-hand corner to create a new Custom Credential Type.
4. Set the name of your Credential Type. e.g. `CyberArk PAS REST API`
5. Under `Input Configuration` select `YAML`.
6. Copy and paste the [input.yml](input.yml) into the text field for `Input Configuration`.
7. Under `Injector Configuration` select `YAML`.
8. Copy and paste the [injector.yml](injector.yml) into the text field for `Injector Configuration`.
9. Click `Save` at the bottom to save the Custom Credential Type.


## CyberARk Vault

 When setting up the job in ansible tower you can leverage the `CYBERARK_API_USERNAME` as the name of the user who will logon to the vault

## Create a Job Template in Ansible Tower
To use this playbook on ansible tower you can follow these steps.

 Note: you can also follow the video instructions here: https://www.ansible.com/products/tower/setup

* Login to your ansible tower instances

* Click the add button then select Job Template from the menu list.
* Enter the appropriate details into the following fields:
* Name: Enter a name for the job.
* Description: Enter an arbitrary description as appropriate (optional).
* Job Type: Choose a job type:

*  Run: Execute the playbook when launched, running Ansible tasks on the selected hosts.

*  Check: Perform a “dry run” of the playbook and report changes that would be made without actually making them. Tasks that do not support check mode will be skipped and will not report potential changes.

*  Prompt on Launch: If selected, even if a default value is supplied, you will be prompted upon launch to choose a job type of run or check.


* Inventory: Choose the inventory to be used with this job template from the inventories available to the currently logged in Tower user.

*  Prompt on Launch: If selected, even if a default value is supplied, you will be prompted upon launch to choose an inventory to run this job template against.

*  Project: Choose the project to be used with this job template from the projects available to the currently logged in Tower user.

*  SCM Branch: This field is only present if you chose a project that allows branch override. Specify the overriding branch to use in your job run. If left blank, the specified SCM branch (or commit hash or tag) from the project is used. For more detail, see job branch overriding.

*  Prompt on Launch: If selected, even if a default value is supplied, you will be prompted upon launch to choose an SCM branch.

*  Playbook: Choose the playbook to be launched with this job template from the available playbooks. This field automatically populates with the names of the playbooks found in the project base path for the selected project. Alternatively, you can enter the name of the playbook if it is not listed, such as the name of a file (like foo.yml) you want to use to run with that playbook. If you enter a filename that is not valid, the template will display an error, or cause the job to fail.

*  Credentials: Click the search button to open a separate window. Choose the credential from the available options to be used with this job template. Use the drop-down menu list to filter by credential type if the list is extensive.

* Prompt on Launch: If selected, upon launching a job template that has a default machine credential, you will not be able to remove the default machine credential in the Prompt dialog without replacing it with another machine credential before it can launch. Alternatively, you can add more credentials as you see fit. Below is an example of such a message:

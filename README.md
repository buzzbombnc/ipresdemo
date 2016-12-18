This is an Ansible application deployment playbook written for an interview presentation.

# Requirements

* Controller system:
	* Should be RHEL/CentOS 7.
	* Must have the development group of packages installed.  (`yum groups install development`)
	* Must have openssl-devel and libffi-devel packages installed.  (`yum install openssl-devel libffi-devel`)
	* Must have python-virtualenv package installed to use virtual environment.  (`yum install python-virtualenv`)
	* Must be able to SSH from the controller to each client machine below via SSH key.  (I.e. no password)

* Worker/proxy clients:
	* Should also be RHEL/CentOS 7.  ("minimal" installation is acceptable.)
	* The destination user account should have the ability to `sudo` to the root account via password.

# Usage

1. Clone this repository.
2. (optional, but recommended.)  Build and activate a new virtualenv for Ansible and related modules.  (`virtualenv env && . env/bin/activate`)
3. Install the modules.  (`pip install -r requirements.txt`)
4. Update the `inventory` file with client hostnames.
4. Execute playbook.  (`ansible-playbook -i inventory site.yml`)



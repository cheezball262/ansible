
Environment: RHEL/CentOS, Python >2.7, ansible, ssh key access to target host<br><br>
<b>Ansible Playbooks:</b><br>
**manageUsers.yaml** - will add/remove users from system. 
	

       usage: ansible-playbook manageUsers.yaml 
    	  
    	note: change install_state to present/absent to add remove users
            change username and full_name vars to appropriate vaules.

**listUsers.yaml** - will list all users on the system. 
	

    usage: ansible-playbook listUsers.yaml
    note: this uses the getent ansible module. This will dump the complete output for all the users.
    Could use some filtering to get rid of the non-essential return data.
    
    	
**listUserScript.yaml** - will list all users/userids/comments on the system.
	

     usage: ansible-playbook listUserScript.yaml<userid>
	note: ths playbook executes the listUsers.py python script to list all users and filter the 
	return data. This was a simpler approach and re-used the already working script rather than 
	burn a bunch of cycles figuring out a filter for the JSON returned by getent.  


Ansible - Setup SSH keys and Create user accounts at the target host and deploy the ssh keys to the Target host users
=====================================================================================================================

1. Create a SSH key in your Ansible Master node (Localhost)
2. Create a list of user names for your target host
3. Create a user account for each user name in the Target host
4. Deploy the Ansible Master node SSH (Pub key) to Target host users  
5. Allow Admin group users to sudo without password ,Modify /etc/sudoers so the users can use sudo without entering a password
6. Update sshd config to disable root login and restart ssh service

Note: before executing the playbook your masternode /root/.ssh/id_rsa.pub  key should be copied  on the Target host /root/.ssh/authorized_keys

After implemting all the above steps you will be able to login to the target host users from Ansible Master node without any password.

Playbooks Execution

a. Executing the playbook for creating ssh key in the localhost

ansible-playbook create-ssh-key.yml

b. Executing the playbook for deploying the new users along with the localhost ssh keys into the users

ansible-playbook users.yml -vvv


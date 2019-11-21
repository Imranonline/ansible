# ansible

Ansible QuickStarters

### Create Ansible Server (Lets take an example of Ubuntu 18.0 as an Ansible Server)

1. Create a machine using Ubuntu 18.0 AMI.
2. Save the pem key with name ansible.pem
3. Install Ansible on that server

<pre><code>sudo apt update
sudo apt install software-properties-common</pre> </code>

Then add the Ansible PPA by typing the following command:

<pre><code>sudo apt-add-repository ppa:ansible/ansible</pre></code>

Press ENTER to accept the PPA addition.

Next, refresh your system’s package index once again so that it is aware of the packages available in the PPA:

<pre><code>sudo apt update</pre></code>

Following this update, you can install the Ansible software:

<pre><code>sudo apt install ansible
ansible --version</pre></code>

Your Ansible server now has all of the software required to administer your hosts.

Ansible uses a python interpreter located at /usr/bin/python to run its modules, you’ll need to install Python 2 on the host in order for Ansible to communicate with it. Run the following commands to update the host’s package index and install the python package:

<pre><code>sudo apt update
sudo apt install python</pre></code>

4. Creating New Ansible hosts

Please create 2 -3 machines as Linux Centos Distribution.

5. Setting Up Ansible Hosts

Copy the pem key in the main location.
type pwd to get the location of the file

Open the file with sudo privileges, like this:

<pre><code>sudo vi /etc/ansible/hosts</pre></code>

you can give any group name like my_grp etc.

<pre><code>
[my_grp]
www1-gcp

[my_grp:vars]
ansible_ssh_user=ec-2 // This will be the user of the machine based on machine type for aws ec-2
ansible_ssh_private_key_file=./mykey.pem // your Pem key location.
</pre></code>

6. Type Ansible Ping Command to check if Hosts are active

<pre><code>ansible -m ping all</pre></code>

7. Create an ansible playbook
   see file install-ansible.yml

8. Run the Ansible Playbook.

<pre><code>ansible-playbook install-nginx.yml</pre></code>

We could also specify an individual host:

<pre><code>ansible -m ping my_grp</pre></code>

We can specify multiple hosts by separating them with colons:

<pre><code>
ansible -m ping my_grp:my_grp2</pre></code>

The "shell" module lets us send a terminal command to the remote host and retrieve the results. For instance, to find out the memory usage on our host1 machine, we could use:

<pre><code>
ansible -m shell -a 'free -m' my_grp
</pre></code>

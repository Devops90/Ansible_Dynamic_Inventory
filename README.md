# Ansible_Dynamic_Inventory.
aws cloud dynamic inventory.
Create two files ec2.py and ec2.ini in ansible installation patch /etc/ansible.
Give Execute permissions to ec2.py file (chmod 766 ec2.py).
Run ec2.py file (./ec2.py), get error (/usr/bin/env: ‘python’: No such file or directory) .
set python version, provide soft link to python2.7 alrady installed (ln -s /usr/bin/python2.7 /usr/bin/python) in /usr/bin location.
run ec2.py file (./ec2.py) get error (ImportError: No module named boto), then install boto package
pip2 install boto (install boto package).
run ec2.py file get error ('Check your credentials' % (len(names), str(names)))), then add IAM role to ec2 instance (ansible run on that ec2 instance).
run ec2.py get error (ERROR: "Forbidden", while: getting ElastiCache clusters[root@ip-172-31-47-42 ansible]#), then open ec2.ini and uncommant elasticache.
eun ec2.py get all running ec2 instances in aws accoubt. 
generate ssh connetion between server.
ansible -i ec2.py ec2 -m ping (here ec2 is servers group).
ansible -i ec2.py ec2 -m command -a "cat /etc/passwd" .
ansible -i ec2.py ec2 -m file -a "path=/opt/file1 state=touch" .
ansible-playbook sample.yml -i ec2.py (run ansible playbook on dainamic inventory).

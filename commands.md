## Commands used 

```
-- To install Ansible on Master server --
sudo apt update
sudo apt install ansible -y
```


```
-- To check the version of ansible --
ansible --version
```


```
-- Create ansible_key on Master server --
cd .ssh
vim ansible_key
```


```
-- To SSH into a node server --
sudo ssh ubuntu@[ip adress] -i ~/.ssh/ansible_key
```


```
-- To check your Inventory file location --
cat /etc/ansible/hosts
```


```
-- Create an Inventory file in /ansible dir --
mkdir ansible
cd ansible
vim hosts
```


```
-- To check your Inventory file validity --
ansible-inventory --list -y -i /home/ubuntu/ansible/hosts
```


```
-- Give permissions to /.ssh dir and hosts file --
chmod 700 ~/.ssh
chmod 600 ~/.ssh/ansible_key
```


```
-- To ping all the servers in hosts --
ansible all -m ping -i /home/ubuntu/ansible/hosts --private-key=~/.ssh/ansible_key
```


```
-- Check Disk Space of servers --
ansible all -a "free -h" -i /home/ubuntu/ansible/hosts --private-key=~/.ssh/ansible_key
```


```
-- To check uptime of servers --
ansible all -a "uptime" -i /home/ubuntu/ansible/hosts --private-key=~/.ssh/ansible_key
```




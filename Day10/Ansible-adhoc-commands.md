## Ansible Adhoc Commands:


1. Syntax:
```
ansible <hosts> [-m <module_name>] -a <"arguments"> -u <username> [--become]  
```

2. To run reboot for all your company servers in the group, 'abc', in 12 parallel forks:

```
$ ansible abc -a "/sbin/reboot" -f 12  

$ ansible abc -a "/sbin/reboot" -f 12 -u username  
```

3. File Transfer:
You can use ad-hoc commands for doing SCP (secure copy protocol) which means lots of files in parallel on multiple machines or servers.

Transferring file on many machines or servers:
```
$ ansible abc -m copy -a "src = /etc/yum.conf dest = /tmp/yum.conf"  
```

Creating new directory: 
```
$ ansible abc -m file -a "dest = /path/user1/new mode = 888 owner = user1 group = user1 state = directory" 
```
Deleting all directory and files:

```
$ ansible abc -m file -a "dest = /path/user1/new state = absent"  

```

4. Managing Packages:
Ad-hoc commands are available for apt and yum module. Here are the following ad-hoc commands using yum.

Below command checks, if the yum package is installed or not, but not update it.
```
$ ansible abc -m yum -a "name = demo-tomcat-1 state = present" 
```
Below command checks the package is not installed.
```
$ ansible abc -m yum -a "name = demo-tomcat-1 state = absent"   
```

And below command checks the latest version of package is installed.
```
$ ansible abc -m yum -a "name = demo-tomcat-1 state = latest"   
```

5. anaging Users and Groups:
You can manage, create, and remove a user account on your managed nodes with ad-hoc commands.

```
$ ansible all -m user -a "name=foo password=<crypted password here>"  
  
$ ansible all -m user -a "name=foo state=absent"
```  


6. Managing Services:

Ensure a service is started on all the webservers.
```
$ ansible webservers -m service -a "name=httpd state=started"  
```
Alternatively, restart a service on all webservers:
```
$ ansible webservers -m service -a "name=httpd state=restarted" 
```
Ensure a service is stopped:
```
$ ansible webservers -m service -a "name=httpd state=stopped"
```


7. Gathering Facts:

Fact represents the discovered variables about a system. You can use the facts to implement conditional execution of tasks, and also used to get ad-hoc information about your systems. To see all the facts:
```
$ ansible all -m setup  
```

8. 


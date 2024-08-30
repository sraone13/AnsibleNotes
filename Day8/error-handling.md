Error handling: 

When any tasks gets failed in managed nodes, ansible it will not excute the second task
its a by default in ansible.

We can controle that error by error handling 
ignore_errors: yes

If task 1 fails, it will ignore that task 1 and will continue with second task

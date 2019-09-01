### To create a new file using playbook
```
---
- hosts: all
  become: True
  tasks:
   - name: create a file
     file:
      path: /home/ec2-user/new-ans.txt
      state: touch
...
```



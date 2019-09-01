### To create a new file using playbook

$ vi new.yml
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

### To run the ansible playbook
```
$ ansible-playbook new.yml
```


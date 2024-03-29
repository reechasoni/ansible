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

### in hosts file mention the below things
$ vi /etc/ansible/hosts
```
172.31.13.82 ansible_user=ec2-user ansible_ssh_private_key_file=~/dev.pem ansible_connection=ssh
```

### To create and write some content in particular file
```
---
- hosts: all
  become: True
  tasks:
   - name: create a file
     file:
      path: /home/ec2-user/content.txt
      state: touch
      mode: 600
   - name: copy the content
     copy:
      dest: "/home/ec2-user/content.txt"
      content:
        hi this is my new file
        this is second line
...

```

### To create multiple files using ansible playbook

```
---
- hosts: all
  become: True
  tasks:
    - name: create multiple files
      file:
        path: "/home/ec2-user/{{ item }}"
        state: touch
        mode: 600
      with_items:
      - acees.log
      - test.log
      - ridhi.log

```

### Create multiple file with mode i.e using ansible loops ( with_items )

```
---
- hosts: all
  become: True
  tasks:
    - name: create multiple file with mode
      file:
        path: "/home/ec2-user/{{ item.location }}"
        state: touch
        mode: "{{ item.mode }}"
      with_items:
      - { location: 'new1.txt' , mode: '600' }
      - { location: 'new2.txt' , mode: '600' }

````


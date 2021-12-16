### Run ansible-playbook [example]
```$ ansible-playbook -i ansible/hosts ansible/playbook-ssh.yml```

### Run ansible with module ping
```$ ansible -m ping all -i ansible/hosts```

### Run ansible with module shell
```$ ansible -m shell -a 'uname -a' host0  -i ansible/hosts```

### Run ansible with module copy
```$ ansible -m copy -a 'src=/etc/motd dest=/tmp/' host0 -i ansible/hosts```

### Check Ubuntu version on each machine
```$ ansible -m shell -a 'grep DISTRIB_RELEASE /etc/lsb-release' all -i ansible/hosts```

### More info about machine
```$ ansible -m setup host0 -i ansible/hosts```

### Meminfo
```$ ansible -m setup -a 'filter=ansible_memtotal_mb' host* -i ansible/hosts```

### Run playbook-nginx.yml onto host0
```$ ansible-playbook -i ansible/hosts -l host0 ansible/playbook-nginx.yml```

### Run playbook-mysql.yml onto host0
```$ ansible-playbook -i ansible/hosts ansible/playbook-mysql.yml -l host0```

### Restart nginx.service onto host0
```$ ansible -b -i ansible/hosts -m service -a 'name=nginx state=restarted' host0```

### Install git onto host0
```$ ansible-playbook -i ansible/hosts ansible/playbook-git.yml -l host0```

### Install php onto host0
```$ ansible-playbook -l host0 playbook-php.yml```

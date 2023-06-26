#### 1. Ansible adhoc command(s) to copy a file with content "This is my first web page" to a destination /var/www/html/index.html and give permission to the file as 644 on your target machine and verify the same using adhoc command from control machine itself.

```
tuttu@techtraining1:~$ ansible -i inventory.ini 192.168.10.107 -m copy -a "content='This is my first web page' dest=/var/www/html/index.html mode=0644" --become --ask-become-pass
BECOME password:
192.168.10.107 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "checksum": "d23da7d6c555a124f173b94c9e5b475f0ef0cf98",
    "dest": "/var/www/html/index.html",
    "gid": 1013,
    "group": "tuttu",
    "mode": "0644",
    "owner": "tuttu",
    "path": "/var/www/html/index.html",
    "size": 25,
    "state": "file",
    "uid": 1013
}


tuttu@techtraining1:~$  ansible -i inventory.ini 192.168.10.107 -m stat -a "path=/var/www/html/index.html"
192.168.10.107 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "stat": {
        "atime": 1687677161.8816082,
        "attr_flags": "e",
        "attributes": [
            "extents"
        ],
        "block_size": 4096,
        "blocks": 8,
        "charset": "us-ascii",
        "checksum": "d23da7d6c555a124f173b94c9e5b475f0ef0cf98",
        "ctime": 1687677107.077361,
        "dev": 2050,
        "device_type": 0,
        "executable": false,
        "exists": true,
        "gid": 1013,
        "gr_name": "tuttu",
        "inode": 1458059,
        "isblk": false,
        "ischr": false,
        "isdir": false,
        "isfifo": false,
        "isgid": false,
        "islnk": false,
        "isreg": true,
        "issock": false,
        "isuid": false,
        "mimetype": "text/plain",
        "mode": "0644",
        "mtime": 1687677105.985357,
        "nlink": 1,
        "path": "/var/www/html/index.html",
        "pw_name": "tuttu",
        "readable": true,
        "rgrp": true,
        "roth": true,
        "rusr": true,
        "size": 25,
        "uid": 1013,
        "version": "4200433304",
        "wgrp": false,
        "woth": false,
        "writeable": true,
        "wusr": true,
        "xgrp": false,
        "xoth": false,
        "xusr": false
    }
}

```

####  Ansible playbook to install httpd using variables and start and enable services with the same variable tags on your target machine.





2. Ansible playbook to install httpd using variables and start and enable services with the same variable tags on your target machine.

# Playbook
## play
- Defines a set tasks to be run hosts
- Task: An action to be performed on the host
+ Excute command
+ run a script
+ install a package
+ shutdown/restart
# RUN
## excute ansible playbook
|ansible|ansible-playbook|
|-------|----------------|
|ansible <hosts> -a <command> | ansible-playbook <playbook name>|
|ansible all -a "/sbin/reboot"| ansible-playbook playbook-webserver.yaml |
|ansible <hosts> -m <module>|  |
|ansible target1 -m ping | |
#   MODULE
##  System
- System is a acction excute at a system level
- User, Group, hostname, iptables, Lvg, Lvol, Make, Mount, Ping, Timezone, systemd, Service
### service
- manage services - start, st, restart
```sh
-
    name: Start Service in order
    host: localhost
    tasks:
     - name: Start the database service
       service: name=postgresql state=started
     - name: Start the nginx service
       service:
         name: nginx
         state: started
        
```
**started,restarted, stopped**

## Commands
- used to excute command or script on a host (command, expect, raw, script shell)
### command
- chdir: cd into the directory before running the command
- creates: filename if it already exits, this step will not be run
### script
- run a local script on a remote node 
- 
## File
-  helping work with file
### lineinfile
- Search for a line  in a file and replace it or add it if it doesnlt exits. 
- .
`/etc/resolv.conf`
```sh
nameserver 10.2.250.1
nameserver 10.1.250.0
```
`playbook.yml`
```sh
-
    name: Add DNS server to resolv.conf
    hosts: localhost
    tasks:
      - lineinfile:
            path: /etc/resolv.conf
            line: 'nameserver 10.1.250.10
```
## database
- helping working with database
## cloud
 - helping work with cloud (aws, azure,...)

# Variable
- stores information  that varies with each host


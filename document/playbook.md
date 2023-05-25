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
```sh
|ansible|ansible-playbook|
|-------|----------------|
|ansible <hosts> -a <command> | ansible-playbook <playbook name>|
|ansible all -a "/sbin/reboot"| ansible-playbook playbook-webserver.yaml |
|ansible <hosts> -m <module>| |
|ansible target1 -m ping ||

```


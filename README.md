# ansible-restic-backup
A simple approach to backup a fleet of servers from central server using ansible

This is just a backup strategy I invented and used to backup hundred of servers using ansible and restic backup utility which features out of the box encryption, de-duplication along with real-time repository mounting using fuse userspace (to restore files as fast as possible).

All backup encryption keys will be saved in your ansible controller and mounted repo can be accessed by root user only.

All configurable variables can be found in group_vars/all and those can be overriden per host.

If you want to backup using SFTP make sure to setup key-based ssh authentication between your source server and destination backup server.

after you set your inventory and your hosts desired variables run
```bash
ansible-playbook -i inventory playbook.yaml
```


# Autofs Configure




## Server Side Configuration

Install nfs packages

```bash
  yum Install nfs-utils -y
```
Restart nfs serice

```bash
systemctl start nfs
```
Add user with username

```bash
  useradd remoteuser
```
Give password to useradd

```bash
passwd remoteuser
```
Put entry inside the /etc/exports file

```bash
vim /etc/exports

/home/username  *(rw,sync)
```
Execute command 

```bash
exportfs -r
```
## Client Side Configuration

Install autofs packages

```bash
yum install autofs -y
```
Add user with (any name)

```bash
  useradd (remoteuser)
```

Remove remoteuser home directory

```bash
rm -rf /home/remoteuser
```
Now swith user remoteuser

```bash
su remoteuser
```
Now you can see only bash shell like this:

```bash
[sh.11]$
```
Putt entry of /home directory in /etc/auto.master

```bash
vim /etc/auto.master

/home  /etc/auto.misc
```
Putt entry of remoteuser directory in /etc/auto.misc

```bash
vim /etc/auto.misc

remoteuser  -rw,sync ip address:/home/remoteuser
```
Restart the autofs service

```bash
systemctl restart autofs
```
After the autofs configuration when you switch user command you can see:

```bash
[remoteuser]$
```

## Important note

Now we can geting remoteuser home directory from the server Side,because we deleted user home directory from client side.This is called autofs service and on demand mount.Always remember selinux will stop as well as firewalld.service will also stop.
setenforce 0 (To stop selinux)
systemctl stop firewalld.service (To stop firewalld service)


## Authors

- [@Nirbhai-Singh](https://www.github.com/octokatherine)


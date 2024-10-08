# Finding files
We know how to list,create and read files. But when multiple directories contain files with same name, we might need to find all those files available. So we use `find` command. In find command, we give
*search criteria* and *search location* as the optional arguments. If search location is not mentioned, find uses current working dictionary(.) as the search location. Also if we wanna filter by certain conditions like name, etc.., we give it as search criteria.
	In this challenge, our flag is hidden in a random directory. But, this filesystem also contains multiple files named flag in different directories. And some directories are also restricted
permission to access, so in order to find accessible directories, I used `-name` as my search criteria
which weeded out the restricted directories. Then out of accessible directories, I did trial and error to find suitable directory that contains the needed flag file with the flag in it.

```bash
hacker@commands~finding-files:~/profile$ cd /
hacker@commands~finding-files:/$ ls
bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~finding-files:/$ find / -name flag
/home/hacker/flag
find: ‘/tmp/tmp.MiOQGWw5Zc’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/local/share/radare2/5.9.5/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/linux/linux-5.4/drivers/base/power/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/radare2/libr/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag
/nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
hacker@commands~finding-files:/$ cd /opt/linux/linux-5.4/drivers/base/power/flag
ssh-entrypoint: cd: /opt/linux/linux-5.4/drivers/base/power/flag: Not a directory
hacker@commands~finding-files:/$ cd /opt/linux/linux-5.4/drivers/base/power
hacker@commands~finding-files:/opt/linux/linux-5.4/drivers/base/power$ cat flag
pwn.college{YEb3-y2poVDVSrWsFtSfAfQf3ML.dJzM4QDL2kTN0czW}
```

## References Used:
None

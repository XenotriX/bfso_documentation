# Permissions

#### Default Permissions

* 755 for directories and 644 for files
* no execute permissions, everyone can read, and only the user can write

#### d rwx rwx rwx

* d = directory, l = symbolc link, - file
* rwx = Owner permission
* rwx = Group permission
* rwx = All other users permission

#### Change the permission of an folder

```text
chmod -R 755 /var/www/html/typo3/
```

#### Change owner and group of folder

```text
chown -R centos:apache /var/tmp/automysqlbackup
```

* centos: new owner
* apache: new group

{% embed url="https://codesport.io/security/the-ulitmate-guide-to-file-and-directory-permissions-on-ubuntu/" %}

{% embed url="https://www.unixtutorial.org/difference-between-chmod-and-chown" %}


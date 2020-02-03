# User and Groups

#### Create new user

```text
adduser christoph
passwd christoph
```

#### Change the owner of an folder

```text
chown christoph /opt/casgatedev-christoph
```

#### Switch to a different user

```text
su <username>
```

#### Show all users in the group \`apache\`

```text
grep 'apache' /etc/group
```

#### Add a user to a group

```text
usermod -a -G apache centos
```

#### List all local groups

```text
cut -d: -f1 /etc/group | sort
```

#### Change your password

```text
passwd
```

#### Change your account informations

```text
chfn
```


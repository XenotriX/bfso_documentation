# System



#### Help

Show help about a command

```text
man
man ls
```

#### restart/reboot

```bash
	systemctl reboot
```

## System Information

#### Show Kernel Version

```text
lsb_release -a

#oder

uname -a
```

#### Show Hostname

```text
hostname
```

#### Change Hostname

```text
sysctl -w kernel.hostname=bsfo-srv-ls-typo3-001
```

#### Show available disk space

```text
df -H

Filesystem                               Size  Used Avail Use% Mounted on
/dev/mapper/root_vg-root_lv               29G  2.8G   27G  10% /
[..]
```

#### Show processes

```text
ps aux
top
ps -A
```

#### Show processes for a certain user

```text
ps aux | grep christo
```

#### Stop a process

```text
kill -9 163
```

#### Stop what are you doing

```text
CTRL+C
```

## Partitionen

```text
df -h
```


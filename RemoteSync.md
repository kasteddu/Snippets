***Remote sync for 2 servers***


Grab a remote file from a local server -- ie nightly backup of data

```bash
rsync -r -a -v -e "ssh -l [USER] -p [PORT]" --delete  [REMOTE SERVER IP]:[REMOTE SERVER PATH] [LOCAL SERVER PATH]
```


Syntax: 

```bash
scp <source> <destination>

```

To copy a file from B to A while logged into B:

```bash
scp /path/to/file username@a:/path/to/destination

```

To copy a file from B to A while logged into A:

```bash
scp username@b:/path/to/file /path/to/destination

```

Add -i /path/to/cert

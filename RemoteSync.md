***Remote sync for 2 servers***


Grab a remote file from a local server -- ie nightly backup of data

```bash
rsync -r -a -v -e "ssh -l [USER] -p [PORT]" --delete  [REMOTE SERVER IP]:[REMOTE SERVER PATH] [LOCAL SERVER PATH]
```

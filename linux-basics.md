# Linux command line basics

The commands I use most when I support or set up Linux machines. Examples use Ubuntu/Debian.

## Moving around and looking at files

```bash
pwd                  # where am I
ls -la               # list files, including hidden ones, with permissions
cd /var/log          # go to a folder
cat file.txt         # print a file
less file.txt        # read a long file (q to quit)
tail -f /var/log/syslog   # follow a log live
grep -i "error" file.log  # search text
```

## Files and folders

```bash
mkdir projects
cp file.txt backup/       # copy
mv old.txt new.txt        # move or rename
rm file.txt               # delete a file
rm -r folder              # delete a folder (careful)
```

## Permissions

```bash
ls -l script.sh          # -rwxr-xr-- 1 user group ...
chmod +x script.sh       # make it executable
chmod 640 notes.txt      # owner read/write, group read, others nothing
chown user:group file    # change owner
```

The three groups of letters are owner, group and others. `r` = 4, `w` = 2, `x` = 1, so `640` is
`rw-` `r--` `---`.

## Users and sudo

```bash
whoami
sudo command             # run one command as administrator
sudo adduser maria
```

## Installing software

```bash
sudo apt update
sudo apt install htop
sudo apt remove htop
```

## Processes and resources

```bash
ps aux | grep nginx
top                      # or htop if installed
df -h                    # disk space
free -h                  # memory
kill <pid>
```

## Services

```bash
systemctl status ssh
sudo systemctl restart ssh
sudo systemctl enable ssh      # start at boot
journalctl -u ssh --since "1 hour ago"
```

## Network

```bash
ip addr
ip route
ping -c 4 8.8.8.8
ss -tulpn                # listening ports
curl -I https://example.com
```

## Habits that save time

- Read the error message completely before searching for it.
- Look at the logs (`journalctl`, `/var/log`) before changing anything.
- Make a copy of a configuration file before editing it: `sudo cp file file.bak`.

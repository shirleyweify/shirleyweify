# Commands

## MacOS Shortcut
| Action | Description |
| ---- | ---- |
| `option` + `command` + `esc` | force to quit |

## MacOS Keyboard

```
launchctl stop com.apple.TextInputSwitcher
launchctl start com.apple.TextInputSwitcher
```

## Basic Linux Command
https://www.guru99.com/linux-commands-cheat-sheet.html

| Command | Description |
| ---- | ---- |
| `ls` | list |
| `ls -a` | include hidden files |
| `ls -l` | more info |
| `cd` | change directory |
| `rm` | delete files |
| `rm -r` | delete recursively |
| `cat` *file* | print file content |

## Copy and Paste
| Command | Description |
| ---- | ---- |
| `mv` | move: https://wangchujiang.com/linux-command/c/mv.html |
| `cp -r` *copypath* *pastepath* | copy & paste recursively: https://wangchujiang.com/linux-command/c/cp.html |
| `scp -r` *copypath* *username@hostname:pastepath* `-P` *port* | remote copy & paste recursively |
| `rsync` | local or remote sync files: https://www.ruanyifeng.com/blog/2020/08/rsync.html |
| `rsync -anruv --include="*/" --include="bs_2020*.sas7bdat" --exclude="*" /mnt/ExtDiskB/TAQMSEC/raw/ /mnt/ExtDiskA/data/raw_2020` | Sync raw data of all stocks in year 2020 only |

## Disk Usage and Filesize
https://webdevetc.com/blog/linux-command-cheatsheet-disk-usage-and-filesize-cheatsheet/

| Command | Description |
| ---- | ---- |
| `df` | total hard drive disk usage |
| `du` | file sizes, total directory sizes: https://www.redhat.com/sysadmin/du-command-options |

## View and Modify
- `vi` / `vim` *file*
- enter `i` to modify
- `esc` to exit modification mode
- input `:wq` & `enter` to save and exit

## SSH Command
- ssh *username@hostname* -p *port*

## Tmux Sessions
https://tmuxcheatsheet.com/

| Command | Description |
| ---- | ---- |
| `tmux ls` | list sessions |
| `tmux new -s` *session* | create a new session |
| `tmux kill-ses -t` *session* | kill a session |
| `tmux a -t` *session* | attach a session |

| Action | Description |
| ---- | ---- |
| `ctrl` + `b`, `$` | rename |
| `ctrl` + `b`, `d` | detach from a session |
| `ctrl` + `b`, `s` | show all sessions |
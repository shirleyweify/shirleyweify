# Commands

## MacOS Keyboard
- launchctl stop com.apple.TextInputSwitcher
- launchctl start com.apple.TextInputSwitcher

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
| `cp -r` *copypath* *pastepath* | copy & paste recursively |
| `scp -r` *copypath* *username@hostname:pastepath* `-P` *port* | remote copy & paste recursively |

## View and Modify
- `vi` / `vim` *file*
- enter "i" to modify
- "esc" to exit modification mode
- input ":wq" & "enter" to save and exit

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
| ctrl + b, $ | rename |
| ctrl + b, d | detach from a session |
| ctrl + b, s | show all sessions |
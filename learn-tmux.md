To install tmux
On apt: `sudo apt-get install tmux`.

Open tmux:
- run `tmux` and it will show green bar on the bottom.

`[name-session] 0:nvim*`

`[name-session]` the name of the session where you're working on.
`0:nvim` the window name; `0` page of the window and `:nvim` the name of the window and the `*` your current window.

To run command tmux:
`ctrl+b <command>`

Panes on tmux:
Vertical split pane:
`ctrl+b %`
Horizontal split pane:
`ctrl+b "`
Exit on pane:
`exit`
Move in your diffrent pane use the arrow keys:
`ctrl+b <` - Move to the left pane;
`ctrl+b > - Move to the right pane;
`ctrl+b ^ - Move to the up pane;
`ctrl+b v - Move to the down pane;
Resize your panes with arrow keys:
Vertical Pane:
`ctrl+b ctrl+>` - Resize to the left;
`ctrl+b ctrl+< - Resize to the right;
Horizontal Pane:
`ctrl+b ctrl+^ - Resize to the top;
`ctrl+b ctrl+v - Resize to the bottom;
Move through panes in order.
`ctrl+b O`
Swap position of the current pane with the next:
`ctrl+b {`
Swap position of the current pane with the previous:
`ctrl+b }`
Close current pane:
`ctrl+b X`

Windows on tmux:
Create a new window:
`ctrl+b c`
Move on your last window:
`ctrl+b l`
Move on your next window:
`ctrl+b n`
Rename your window:
`ctrl+b ,`
Detached on your window:
`ctrl+b d`

Session on tmux:
List sessions:
`ctrl+b S`
Rename current session:
`ctrl+b $`
Detach current session:
`ctrl+b D`

Commands on tmux:
List of the sessions:
`tmux ls`
Attached on session:
`tmux attach -t <session-name>`
Rename your session:
`tmux rename-session -t <session-name> <renamed-session>`
Create a session:
`tmux new -s <session-name>`
Kill a session:
`tmux kill-session -t <session-name>`

How to copy paste on tmux:
First, you must on copy mode with `Ctrl+b [` then highlight that you want to copy.
To paste the clipboard `ctrl+b ]`

Source file:
`tmux source-file <path-to-.tmux.conf>`
Open tmux and applied the tmux.config:
create a `.tmux.conf` on your home directory

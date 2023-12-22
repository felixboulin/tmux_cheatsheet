# Basic commands to navigate sessions and windows with tmux.

Note: `C-a` refers to control + leader key as defined within tmux
assuming leader is set to 'a'.
## Sessions
Initiate a new session named '<session>' with `tmux new -s <session>`.

To kill it, run `tmux kill-ses -t <session>`.

List all sessions with `tmux ls` and attach to mysession  with 
`tmux a -t mysession`.
Attach to the last session with `tmux a`.

Tigger Window Preview with `C-a+w`, and move between sessions with `C-a+(` and `C-a+)`.

## Windows
Add <window> to the session initiation: `tmux new -s <session> -n <window>`

Create a new window with `C-a+c` and rename the current window with `C-a+,`.
To close it, hit `C-a+&`.
Go to next / previous windows with `C-a+n` and `C-a+p` ; `C-a+[0-9]` to go to
the corresponding window number, and `C_a+l` to toggle last window.

### Swapping windows
`:swap-window -t -1` will move the current window by one place to the left. 

`:swap-window -s 2 -t 1` will swap windows number 2(src) and 1(dst).

#### between sessions
`:move-window -s <session>:<index or name>` will move the window from the session 
specified at given index or name into the active session.

## Panes
`:split-window -h` or `C-a+%` will split the current window into two horizontal 
panes (Vertical: `-v` or `"`).

Toggle last active pane with `C-a+;`, next pane with `C-a+o`

Access a pane with `C-a+q + [0-9]`, it will momentarily reveal pane numbers
then input a number to navigate to it.

Hit `C-a+<space>` to toggle different window arrangement layouts.

`C-a+x` to close the current pane.

`C-a+!` to convert current pane to a window. 

`c-a + C-<any arrow>` and keep pressing control + repetitive <arrow> to resize
window dimension by +1 in the pointed direction.

### Joining
`:join-pane -s 2 -t 1` merge window 2 to window 1 as panes
`:join-pane -s 2.1 -t 1.0` move pane 1 from window 2 to window 1 pane 
afer 0.

`:break-pane` will transform panes into windows.

## Copy mode
Press `C-a+[` to enter copy mode. Vim like motions with `<space>` to start 
selection and `return` to copy.

## Other
`C-a+:<commands>` to enter tmux commands


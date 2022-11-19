# open_with_terminator

When Bash is invoked, check if the terminal proccess is that of a gnome-terminal.
If it is, open a terminator session from the gnome-terminal and then close the gnome-terminal.

One of the effects is having 'Open in Terminal' switch to Terminator instead of using gnome-terminal. 

Add the following to your remote code file (.bashrc in Ubuntu based distros):

```shell
# check if the current terminal is gnome-terminal
# if it is, open a terminator session from gnome-terminal
# then close the gnome-terminal
if ps -o cmd= -p $(ps -o ppid= -p $$) | grep -q gnome; then
  nohup terminator &> /dev/null &
  sleep 0.1s
  exit
fi
```

(taken from https://askubuntu.com/questions/692599/how-to-make-open-in-terminal-in-the-right-click-menu-use-terminator-instead-of)

# open_with_terminator
'Have Open in Terminal' use Terminator.
(taken from https://askubuntu.com/questions/692599/how-to-make-open-in-terminal-in-the-right-click-menu-use-terminator-instead-of)

Add the following to your remote code file (.bashrc in Ubuntu):

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

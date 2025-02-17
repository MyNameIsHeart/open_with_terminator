# open_with_terminator

Add the following to your remote code file:

```shell
if ps -o cmd= -p $(ps -o ppid= -p $$) | grep -q gnome; then
  nohup terminator &> /dev/null &
  sleep 0.1s
  exit
fi
```

### Why?

Doesn't typing every command seem slow?

...

-   Helpful completions

_TeacherNote:_
Add following to `.bash_profile`

```
ip() {
  ifconfig | grep "inet " | grep -Fv 127.0.0.1 | awk '{print $2}' | tee /dev/tty | pbcopy
}
serve() {
    python -m SimpleHTTPServer
}
```

Start local server

```
serve
```

Find ip address

```
ip
```

Find which process listening to port

```
cd {some other directory}
serve #errors
lsof -i :8000
kill -9 {pid}
serve
```

| [Next (Navigation)](Navigation.md) |
| ---------------------------------- |

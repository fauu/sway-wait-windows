# sway-wait-windows

> On Sway, wait for windows to appear and run commands for them

A script that waits for declared Sway windows to appear and then runs commands
for them. It terminates after all provided rules have been applied or after
`--timeout` (default = `30`).

Window rules are accepted through stdin.

## Usage example

```sh
echo ':app org.gnome.Calculator  floating enable
      :title gedit$              move workspace 3, fullscreen enable' \
  | ./sway-wait-windows &
gnome-calculator &
gedit &
```

The directive `:app org.gnome.Calculator` matches a window with either `app_id`
or window 'instance' containing `org.gnome.Calculator`.

The directive `:title gedit$` matches a window with a title ending with `gedit`.

The directives can be combined to require a match for both `app_id`/`instance`
and `title`.

## Dependencies

- Python 3 (recent)
- `i3ipc` Python package (Arch: `python-i3ipc`)

## Credits

Inspired by [i3-toolwait](https://gitlab.com/wef/dotfiles/-/blob/master/bin/i3-toolwait).

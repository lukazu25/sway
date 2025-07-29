## Sway

copy sway folder to sway directory
```bash
sudo cp -r sway ~/.config/sway/
```
 copy waybar config to waybar directory
```bash
sudo cp -r waybar ~/.config/waybar/
```

### Lock on suspend 

Create the following service which locks the screen

`/etc/systemd/system/swaylock@.service`

Check wayland environment variables

```
echo $WAYLAND_DISPLAY
echo $XDG_RUNTIME_DIR
```

```
[Unit]
Description=Lock screen before suspend
Before=sleep.target

[Service]
Environment=XDG_RUNTIME_DIR=/run/user/1000
Environment=WAYLAND_DISPLAY=wayland-1
ExecStart=/usr/bin/swaylock
User=yourusername

[Install]
WantedBy=sleep.target
```
Enable the `swaylock@user.service` systemd unit for it to take effect for the username user

```
sudo systemctl enable swaylock@username.service

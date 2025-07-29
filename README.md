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

Configure **systemd-logind** and Edit `/etc/systemd/logind.conf`

Set the following

```
HandleLidSwitch=suspend
HandleLidSwitchDocked=suspend
```


# VT-HyprNoir - Hyprland 0.53+ Migration

## Key Changes

### Window Rules (Breaking)
Old: `windowrulev2 = float, class:^(steam)$`
New: `windowrule = float on, match:class ^(steam)$`

Block syntax for multiple rules:
```
windowrule {
    name = media-players
    match:title = ^(mpv|imv)$
    float = on
    center = on
}
```

### Layer Rules (Breaking)
Old: `layerrule = blur, waybar`
New:
```
layerrule {
    name = waybar-layer
    match:namespace = ^(waybar)$
    blur = true
}
```

### Removed
- `idleinhibit` windowrule (use hypridle)
- `\s` regex (use `[ -]`)

### NVIDIA RTX 4070 SUPER
- `explicit_sync = 2` in render
- `WLR_NO_HARDWARE_CURSORS=0` (works on 555+)
- `__GL_THREADED_OPTIMIZATION=1`
- Gaming tearing rules for Elite, MHW, CP2077

## Install
```bash
cp -r ~/.config/hypr ~/.config/hypr.bak
cp -r hyprland/.config/hypr/* ~/.config/hypr/
cp -r uwsm/.config/uwsm/* ~/.config/uwsm/
hyprctl reload
```

## VRR Keybinds
- SUPER+F10 = VRR on
- SUPER+F11 = VRR fullscreen only
- SUPER+F12 = VRR off

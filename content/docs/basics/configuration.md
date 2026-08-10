---
title: "Configuration"
parent: "Basics"
bookIcon: "settings"
description: "Learn how to configure WayVR through the dashboard or advanced config files."
---

# Configuration

Most users do not ever have to touch a config file!

Almost all configuration is done via the Dashboard's Settings tab. 

For advanced setups, see [wayvr/src/res/config.yaml](https://github.com/wayvr-org/wayvr/blob/main/wayvr/src/res/config.yaml).

Place this file into `~/.config/wayvr/conf.d` in order to make changes:

```sh
wget -O ~/.config/wayvr/conf.d/base.yaml https://raw.githubusercontent.com/wayvr-org/wayvr/refs/heads/main/wayvr/src/res/config.yaml
```

The file is self-documenting, opening and reading it will hopefully answer your questions.

For further questions, reach out to us on Discord or Matrix.

## Custom command bindings

There is a custom binding called Alt Click that may be used to execute arbitrary commands.

To bind Alt-click to your controller:
- WiVRn/Monado: Bind via WayVR dashboard → Settings → Controls
- SteamVR: Bind via SteamVR bindings

For example, here's a setup that adds push-to-talk functionality for the WiVRn microphone:

```yaml
# ~/.config/wayvr/conf.d/ptt.yaml

alt_click_down: ["pactl", "set-source-mute", "wivrn.source", "0"]
alt_click_up: ["pactl", "set-source-mute", "wivrn.source", "1"]
```

(For microphones other than WiVRn, check your source name using `pactl list short sources`)

# Keyboard layouts

### Fcitx5

When using Fcitx5, WayVR will automatically load the layout as you switch.

### Wayland (some desktops)

Some well-behaved Wayland desktops will send us the layout if we poll it. However, polling it is expensive.

There's a `Load` button on the bottom-right of the keyboard. Press it after switching the layout on your main desktop to load that layout.

### Manual

Some desktop environments (notably KDE) don't allow us to read the system keyboard layout. 

In these cases, there's a layout button on top of the num pad that can be used.

Set up your `~/.config/wayvr/conf.d/keymap.yaml` with the layouts you'll be using, example:

```yaml
keyboard_layouts:
  - pl
  - ru
  - us(dvorak)
```

Format is either `layout` or `layout(variant)`. For a list of possible options, see `man xkeyboard-config`.

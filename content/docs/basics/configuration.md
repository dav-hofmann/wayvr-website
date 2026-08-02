---
title: "Configuration"
parent: "Basics"
bookIcon: "settings"
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

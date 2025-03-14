---
weight: 8
title: hyprpolkitagent
---

hyprpolkitagent is a polkit authentication daemon. It is required for GUI applications to
be able to request elevated privileges.

If it's not available in your distro's repositories, you can either [build it from source](https://github.com/hyprwm/hyprpolkitagent)
or use a different agent, e.g. [KDE's one](https://github.com/KDE/polkit-kde-agent-1/).

## Usage

Add `exec-once = systemctl --user start hyprpolkitagent` to your Hyprland config and restart hyprland.
(obviously change that to whatever you are using if you are not using the hypr one)

If Hyprland is started with [uwsm](../../Useful-Utilities/Systemd-start), you can autostart the polkit agent with the command `systemctl --user enable --now hyprpolkitagent.service`.

If you are using a distribution that does not use systemd such as Devuan, you may need to add
`exec-once=/usr/lib64/libexec/hyprpolkitagent` instead.

Other possible paths include
`/usr/lib/hyprpolkitagent` and
`/usr/libexec/hyprpolkitagent`.

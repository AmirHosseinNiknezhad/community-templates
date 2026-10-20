# DriftWM

Updates DriftWM's background, foreground, and normal/focused border colors from Noctalia.

Enable **DriftWM** in **Noctalia Settings -> Templates**. The template writes `$XDG_CACHE_HOME/noctalia-driftwm-colors` (`~/.cache/noctalia-driftwm-colors` by default).

## Setup and hook

Create your DriftWM config at `$XDG_CONFIG_HOME/driftwm/config.toml` (`~/.config/driftwm/config.toml` by default) before enabling. The Bash hook requires both that config and the rendered colors file.

The hook uses `sed` to replace lines beginning exactly with `bg_color = `, `fg_color = `, `border_color = `, and `border_color_focused = `. Ensure those assignments already exist with that spacing: missing keys are not inserted, and indented assignments are not matched.

The config is edited in place without a backup; save a copy first. The hook does not issue a compositor reload command.

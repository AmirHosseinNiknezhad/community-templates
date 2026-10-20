# Pywalfox

Writes a Pywal-style color palette for Firefox theming through Pywalfox.

Install and configure the Pywalfox Firefox extension and its native host before enabling **Pywalfox** in **Noctalia Settings -> Templates**. This template supplies palette data, not the extension or native-host installation.

The output is `$XDG_CACHE_HOME/wal/colors.json`. Back up an existing file first: this shared Pywal cache file is replaced, which can affect other tools that consume it. The palette includes the wallpaper path and selected color slots; several slots are intentionally empty, so it is not a complete general-purpose Pywal palette.

After rendering, the manifest requests Noctalia's built-in `firefox-theme` post-action. There is no shipped shell hook; the actual browser update is delegated to Noctalia's integration.

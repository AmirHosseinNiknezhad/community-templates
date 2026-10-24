# COSMIC

Keeps [COSMIC](https://system76.com/cosmic) applications built on libcosmic in
sync with the Noctalia palette: `cosmic-files`, `cosmic-edit`, `cosmic-term` and
friends.

## What it writes

COSMIC stores its theme in `~/.config/cosmic`:

| Path | Purpose |
| --- | --- |
| `com.system76.CosmicTheme.Dark/v2/` | the derived dark theme libcosmic reads |
| `com.system76.CosmicTheme.Light/v2/` | the derived light theme libcosmic reads |
| `com.system76.CosmicTheme.Dark.Builder/v2/` | palette and inputs `cosmic-settings` edits |
| `com.system76.CosmicTheme.Light.Builder/v2/` | palette and inputs `cosmic-settings` edits |
| `com.system76.CosmicTheme.Mode/v1/is_dark` | selects dark or light at startup |
| `com.system76.CosmicTk/v1/apply_theme_global` | set to `false` so Noctalia keeps GTK/Qt theming |

The file layout and serialization are the same ones `cosmic-settings` persists
after building a theme, so this is equivalent to selecting a custom theme in
Settings. Both modes are written on every apply, which means flipping Noctalia
between dark and light updates COSMIC immediately.

## Requirements

- A COSMIC application launched at least once, so `~/.config/cosmic` exists.
  The template is skipped until then.
- `python3`.

## Tested against

- COSMIC epoch 1.10.0 (`cosmic-files` 1.0.0, `cosmic-edit` 1.0.0) on Arch Linux.

## Reverting

Run the shipped `undo.sh` to remove the generated theme and let libcosmic fall
back to COSMIC's built-in theme:

```sh
bash "${XDG_STATE_HOME:-$HOME/.local/state}/noctalia/community-templates/cosmic/undo.sh"
```

Noctalia currently runs `undo_hook` only for built-in templates, so community
manifests cannot reference the script; it is shipped for manual use until
community templates gain undo support. The derived theme directory is fully
owned by this template, so undoing discards any theme customized in
`cosmic-settings` before the template was enabled.

## Notes

- COSMIC has no dedicated warning color, so Noctalia's `tertiary` is used for it.
- Frosted surfaces are left disabled, matching COSMIC's default appearance.
- The `Builder` config is written so installing `cosmic-settings` later shows
  the palette as a normal custom theme instead of the built-in default.

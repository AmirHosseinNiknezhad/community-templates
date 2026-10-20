# surgedm

Generate a Noctalia color theme for surgedm, including terminal colors, accents, and graph colors with explicit dark and light variants.

Enable **surgedm** in **Noctalia Settings → Templates**. The template writes `$XDG_CONFIG_HOME/surge/themes/noctalia.toml` (normally `~/.config/surge/themes/noctalia.toml`), with the theme name `Noctalia`.

Select the generated theme in your surgedm setup; this template does not modify the application's theme selection. Its post-hook is empty, so it does not reload or restart the application. Keep manual customizations outside the generated file, which is replaced on regeneration.

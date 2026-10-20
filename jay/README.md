# Jay

Generates Noctalia colors for Jay's window borders, title bars, separators, highlights, and attention indicators.

Enable **Jay** in **Noctalia Settings -> Templates**. The rendered fragment is `$XDG_CACHE_HOME/noctalia/templates/jay-theme.toml` (`~/.cache/noctalia/templates/jay-theme.toml` by default).

## Setup and hook

Install Jay and create `$XDG_CONFIG_HOME/jay/config.toml` (`~/.config/jay/config.toml` by default) first. The Bash hook requires both this config and the generated fragment and uses standard tools including `awk`, `grep`, `sed`, and `paste`.

If no `[theme]` table exists, the hook appends the fragment. Otherwise, it inserts the generated theme and removes matching managed color assignments from the existing theme region, retaining other user-defined keys and comments. The merge operates on the text layout of TOML rather than using a TOML parser.

Back up `config.toml` first: no backup is made. The merge replaces the config using a temporary file and `mv`, so a symlink at the config path is replaced rather than written through. No compositor reload command is included.

# Zellij

Generates a `noctalia` theme for Zellij using Noctalia's terminal colors.

## Setup

Install Zellij and enable **Zellij** in **Noctalia Settings -> Templates**. Select the generated theme in `$XDG_CONFIG_HOME/zellij/config.kdl`:

```kdl
theme "noctalia"
```

## Output

- `$XDG_CONFIG_HOME/zellij/themes/noctalia.kdl`

Back up any existing custom theme at this path before enabling it. The template does not edit `config.kdl`. Its example reload hook is commented out, so no hook runs and no configuration touch or reload is requested automatically.

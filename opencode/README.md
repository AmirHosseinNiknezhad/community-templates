# OpenCode

Generates an OpenCode theme in the native V2 theme format (`base` + `dark`) from the Noctalia palette: real Material surfaces and text colors, tinted diff rows (green added / red removed with bright word-level highlights and colored line-number gutters), ANSI-palette syntax and Markdown colors, and categorical hue scales for agent and skill mentions.

Install OpenCode and enable **Opencode** in **Noctalia Settings -> Templates**. The output is `$XDG_CONFIG_HOME/opencode/themes/matugen.json`. Select the custom **matugen** theme in OpenCode; this template does not change your selected theme.

The theme is dark-mode only: OpenCode uses the dark colors when light mode is requested. Requires OpenCode 2.x or newer — older releases only understand the legacy flat theme format this template used to emit.

The generated file is replaced on palette updates, so back up any existing customizations there. OpenCode reads theme files at startup, so restart running sessions to pick up regenerated colors. No hook or reload command is supplied.

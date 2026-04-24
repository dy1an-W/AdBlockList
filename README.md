A supplemental ad-block list and related proxy configuration files.

Files:
- Shadowrocket config: https://raw.githubusercontent.com/dy1an-W/AdBlockList/main/config/sr-dy1an.conf
- Clash config: https://raw.githubusercontent.com/dy1an-W/AdBlockList/main/config/clash-dy1an.yaml
- Ad-block rules: https://raw.githubusercontent.com/dy1an-W/AdBlockList/main/rules/dylan-adBlock.list

Clash config generation:
- Shared template: `config/clash.template.yaml`
- Renderer: `scripts/render-clash-config.sh`
- Local env: `.env`

Usage:
```bash
# Render the file-provider version to FILE_OUTPUT_PATH
scripts/render-clash-config.sh file

# Render the http-provider version to HTTP_OUTPUT_PATH
scripts/render-clash-config.sh http
```

Notes:
- `FILE_OUTPUT_PATH` and `HTTP_OUTPUT_PATH` are read from `.env`.
- `HTTP_OUTPUT_PATH` can point to a symlink; the renderer writes into the linked target instead of replacing the symlink.
- The generated files share the same template body. Only `proxy-providers` differ between modes.

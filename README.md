# Obsidian paste image rename

> [!NOTE]
> This is a fork of [reorx/obsidian-paste-image-rename](https://github.com/reorx/obsidian-paste-image-rename), which has not been maintained since 2023. See the original repository for the full documentation.

Prompts you to rename an image (or any attachment) right after pasting or dropping it into a note, with configurable name patterns such as `{{fileName}}`, `{{imageNameKey}}` or `{{DATE:YYYYMMDD}}`, plus batch renaming of all images in a note.

## Changes in this fork

- **Fix: pasted images were silently ignored** on filesystems that don't report a creation time (e.g. NTFS mounted via FUSE on Linux). The plugin now falls back to the modification time and waits for `workspace.onLayoutReady` instead of relying on timestamps to skip the startup indexing burst.

## Manual installation

1. Download `main.js`, `manifest.json` and `styles.css` from the [latest release](https://github.com/JoshuaDreier/obsidian-paste-image-rename/releases/latest).
2. Copy them into `<your vault>/.obsidian/plugins/obsidian-paste-image-rename/` (create the folder if needed; if the original plugin is installed, overwrite its files).
3. Reload Obsidian, then enable **Paste image rename** under *Settings → Community plugins*.

> [!WARNING]
> The plugin ID is the same as the original's. If upstream ever publishes a newer version, Obsidian's plugin updater may replace this fork with it.

## Building from source

```bash
npm ci
npm run build
```

The built plugin files end up in `build/`.

## License

MIT, see [LICENSE](LICENSE).

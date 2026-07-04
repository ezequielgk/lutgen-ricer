# Lutgen Ricer

A CLI script to automate applying color schemes (palettes) to wallpapers using [lutgen](https://github.com/ozwaldorf/lutgen-rs).
The script automatically syncs your custom palettes from a repository, processes them, and applies them to your images.

## Dependencies

This script requires the following packages installed on your system:

* **lutgen**: https://github.com/ozwaldorf/lutgen-rs
* **jq**: JSON processor.
* **curl**: For downloading the schemes.
* **tar**: For extracting the downloaded schemes.

## Installation

1. Make sure the script has execute permissions:

```bash
chmod +x ricer
```

2. Move the script to your local binaries folder:

```bash
mkdir -p ~/.local/bin
mv ricer ~/.local/bin/ricer
```

3. Make sure `~/.local/bin` is in your `$PATH`. If it isn't, add this to your shell configuration (e.g. `config.fish` or `.bashrc`):

```bash
fish_add_path ~/.local/bin
```

## Usage

Simply run the command in your terminal:

```bash
ricer
```

### How it works:

1. **Sync**: On execution, the script downloads the palette JSON files from the configured repository, processes them, and generates the necessary configuration files in `~/.config/lutgen/`.
2. **Selection**: It will show you an interactive menu to:
   * Choose the folder containing your original wallpapers.
   * Choose between using custom palettes (synced from the repo) or lutgen's built-in palettes.
3. **Processing**:
   * Creates an organized folder structure (`PaletteName/OriginalFolder`).
   * Applies the filter to all images (`jpg`, `jpeg`, `png`, `webp`) within the folder.
   * Processed images are saved automatically, keeping your originals intact.

## Customization

If you want to use your own palette repository, edit the `REPO_URL` variable inside the script:

```bash
REPO_URL="https://github.com/your-user/your-repo"
```

---

Let me know if you'd also want a proper `README.md` file saved for the repo, or if you want me to tweak the tone (more casual vs. more formal for a public release).

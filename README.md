# rofi-hyprshot

Hyprland screenshot menu that packages a `hyprshot` command and a Rofi front
end. It supports full-output, region, and window captures, clipboard copying,
notifications, and basic screen-to-GIF recording.

## Build and install

```bash
nix build github:RevolunixOS/pkg-rofi-hyprshot
nix profile install github:RevolunixOS/pkg-rofi-hyprshot
```

## Usage

Open the graphical menu:

```bash
rofi-hyprshot
```

Use the packaged screenshot helper directly:

```bash
hyprshot -m window
hyprshot -m region
hyprshot -m output -m active
hyprshot -m window --clipboard-only
```

Run `hyprshot --help` for all options. Captures default to the XDG pictures
directory and can be redirected with `HYPRSHOT_DIR`.

## Requirements and limitations

- Requires a running Hyprland session.
- The wrapper provides `jq`, `grim`, `slurp`, `wl-clipboard`, notifications,
  Rofi, wf-recorder, and ffmpeg.
- The Rofi front end expects
  `~/.config/rofi/applets/shared/theme.bash`.
- GIF recording uses a selected region and stops by killing `wf-recorder`.
- The package homepage currently points to an unrelated repository and should
  be corrected.

## License

See [`LICENSE`](LICENSE) and preserve any notices in the vendored scripts.

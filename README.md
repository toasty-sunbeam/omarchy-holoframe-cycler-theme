# Holoframe · Cycler Navigation

An [Omarchy](https://omarchy.org) theme with an animated wireframe-hologram background in blue.

![Cycler Navigation preview](preview.png)

A tilted chart of the inner solar system showing an Aldrin cycler: a ship on a permanent Earth–Mars orbit (1.60 AU semi-major axis, eccentricity 0.393, period 2.135 years). Ghost lines show the previous and next cycles as the orbit turns about 48.7° each time. Earth and Mars meet the ship at every crossing, and an encounter schedule counts down to the next flyby.

Holoframe is a set of five themes, each a single-hue hologram on near-black with bracketed HUD panels, live readouts and scanlines. Every scene is based on real engineering or physics, and all artwork is original and drawn in code.

## Install

```bash
omarchy theme install https://github.com/toasty-sunbeam/omarchy-holoframe-cycler-theme.git
```

## What's included

| File | Purpose |
|---|---|
| `backgrounds/1-cycler-loop.mp4` | Seamless 30-second animated background (2560×1600, H.264). The default. |
| `backgrounds/2-cycler-still.png` | Still version (3072×1920). Switch with `omarchy theme bg next`. |
| `colors.toml` | Palette, plus a gradient window border that fades from the accent to a dim edge. |
| `shell.lock.toml` | Lock screen password field: a translucent card with thick side edges that light up while you type. |
| `icons.theme` | Matching Yaru icon colour. |

Omarchy generates terminal, editor and app colours from `colors.toml`.

## Pausing the animation

Video backgrounds are played by Omarchy's wallpaper daemon, OWE, which already pauses during fullscreen apps. To pause or resume by hand:

```bash
owe pause
owe resume
```

To toggle it with Super+Alt+P, add this to `~/.config/hypr/bindings.lua`:

```lua
o.bind("SUPER + ALT + P", "Pause background animation",
  [[sh -c 'if owe status | jq -e .manual_pause >/dev/null; then owe resume; else owe pause; fi']])
```

## Notes

- The HUD is sized for a 2× display at a 16:10 aspect ratio (rendered for a 3072×1920 panel). It works on other screens, with the HUD text slightly larger or smaller.
- The lock screen shows the current background frozen, with Omarchy's own password field at the centre. Each scene keeps its centre calm for that reason.
- The look is inspired by the holographic loading screens of Mass Effect 2. This project is not affiliated with or endorsed by BioWare or Electronic Arts, and contains no assets from the game.

## Other Holoframe variants

- [Orbital Watch](https://github.com/toasty-sunbeam/omarchy-holoframe-orbital-theme) (green)
- [Dyson Swarm](https://github.com/toasty-sunbeam/omarchy-holoframe-dyson-theme) (orange)
- [O'Neill Habitat](https://github.com/toasty-sunbeam/omarchy-holoframe-oneill-theme) (magenta)
- [Tokamak Reactor](https://github.com/toasty-sunbeam/omarchy-holoframe-tokamak-theme) (amber)

## License

[MIT](LICENSE)

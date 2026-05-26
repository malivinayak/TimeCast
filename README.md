# TIMECAST

A calm, single-screen time-action game built in vanilla HTML5 Canvas.

> **Time moves only when you move.**

Every frame of the world - bullets, enemies, particles, sound - advances in lockstep with the player. Stand still and the arena freezes around you; sprint and the world catches up. The result is a thinking-person's shooter where every encounter is a puzzle you can pause inside of.

---

## ✦ Features

- **Reactive time dilation** - global timescale is driven by player input, not by a fixed tick. Holding position gives you all the time you need to read the room.
- **Time Echo** - record a short loop of your own movement and release it as a ghost that fires alongside you.
- **Hand-tuned aesthetic** - soft vignette, subtle scanlines, low-saturation palette, calm audio mix with a global lowpass that follows the timescale so the soundscape softens with the action.
- **Resume-anywhere save** - local progress, master volume, and a *Calm Mode* (reduced motion / fewer flashes) persist between sessions.
- **Mobile & tablet** - full touch UI with a floating joystick, drag-to-aim, and three on-screen action buttons. Auto-enabled on touch devices.
- **Single file** - the entire game is one `index.html`. No build step, no bundler, no dependencies.

---

## ✦ Controls

### Desktop

| Input | Action |
|---|---|
| **W A S D** / Arrows | Move |
| **Mouse** | Aim |
| **Left Click** | Fire |
| **Shift** | Dash |
| **Space** | Release Time Echo |
| **P** | Pause |
| **R** | Quick retry |
| **Esc** | Return to main menu |
| **Enter** | Start (from menu) |

### Touch (mobile / tablet)

| Control | Action |
|---|---|
| Left joystick | Move |
| Right-side drag | Aim |
| ◉ button | Fire |
| ⚡ button | Dash |
| ⟳ button | Release Time Echo |

The cursor is hidden on touch devices and the touch overlay only appears during active gameplay.

---

## ✦ Settings

A small panel at the top of the screen exposes:

- **Volume** - master gain, persisted between sessions.
- **Calm Mode** - softer flashes, reduced motion. On by default.
- **Pause** - same as pressing **P**.

---

## ✦ Running locally

No tooling required. Open `index.html` directly in any modern browser, or serve the folder with any static server:

```bash
# Python 3
python -m http.server 8000

# Node
npx serve .
```

Then open `http://localhost:8000`.

On `localhost` and `127.0.0.1`, both ad SDKs detect a non-production environment and silently no-op. The game runs identically to the hosted build, minus the ad breaks.


---

## ✦ Tech

- **Vanilla JavaScript** - no framework, no build, no dependencies.
- **HTML5 Canvas** - 2D context with substepped, axis-separated collision so fast movement never tunnels through walls.
- **WebAudio** - every sound is synthesized at runtime through a master compressor, high-shelf cut, and a lowpass filter that follows the timescale. No audio assets are shipped.
- **`localStorage`** - for progress, volume, and Calm Mode preference.
- **CSS-only effects** - vignette, scanlines, and grain are pure CSS overlays.

---

## ✦ Browser support

Tested on current Chrome, Firefox, Safari, and Edge. Mobile Safari and Chrome on Android are first-class targets; the touch overlay is enabled automatically when a coarse pointer is detected.

WebAudio is initialised lazily on the first user gesture (a CrazyGames requirement that also matches Safari's autoplay policy), so the game stays silent until the player clicks **NEW GAME**.

---

## ✦ Credits

**Concept & Direction** - malivinayak.

**Development** - built end-to-end by **Claude Opus 4.7** (Anthropic).

**Prompt engineering** - prompts crafted with **GPT-5.5** (OpenAI).

Built with care. Time is yours.

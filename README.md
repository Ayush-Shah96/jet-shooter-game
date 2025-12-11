**Jet Shooter**

- **Type:** 2D endless shooter (Pygame)
- **Files:** `jet_shooter.py` (main game), `jet_shooter_arcade.py` (alternate skeleton), `requirements.txt`

**Overview**
- **Concept:** You control a fighter with a weapon that can switch between three elements — Air, Water, and Fire. Enemies spawn endlessly (Beginner, Mid, Hard); defeat them to score points. The game uses dark/techy UI styling.

**Controls**
- **Move:** `Arrow keys` or `W/A/S/D`.
- **Fire:** `Space`.
- **Select element (direct):** `1` = Air, `2` = Water, `3` = Fire.
- **Cycle elements:** `Q` (previous) and `E` (next).
- **Quit:** `Esc` or window close.

**Scoring & Lives**
- **Lives:** 3 per run.
- **Points:** +5 per enemy killed.
- **Enemy HP:** Beginner = 1 hit, Mid = 2 hits, Hard = 3 hits.

**Assets**
- Place your custom assets in the `assets/` folder (create if missing). Filenames the game looks for:
  - Player: `player_ship.png` (recommended size used in-game: 160×102 px currently)
  - Enemies: `enemy_beginner.png`, `enemy_mid.png`, `enemy_hard.png` (40×28 px recommended)
  - Projectiles: `projectile_air.png`, `projectile_water.png`, `projectile_fire.png` (will be auto-scaled)
  - Sounds (optional): `fire.wav`, `hit.wav`, `bomb.wav`

- Notes:
  - If an asset file is missing the game will raise an error — this project is configured to use your provided assets permanently (no procedural fallback).
  - Projectiles will fall back to colored circles if a custom projectile image is not present.

**Run (Windows PowerShell)**
1. Create and activate a virtual environment and install dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

2. Run the game:

```powershell
python jet_shooter.py
```

Alternate (Arcade skeleton):
```powershell
python jet_shooter_arcade.py
```

**Customization & Tuning**
- To change spawn frequency, HP, speeds, or scoring, open `jet_shooter.py` and look for the `spawn_enemy`, `Enemy` constructor, and scoring sections.
- To change visual sizes for projectiles or the player, edit the scaling arguments where `pygame.transform.smoothscale` is called (search for `smoothscale`).

**Troubleshooting**
- If the game crashes on start complaining about missing files like `player_ship.png`, add the required PNG(s) to `assets/` before running.
- Audio may not initialize on some systems — the code guards mixer initialization; missing sound files are optional.

**Next steps / Suggestions**
- Add more SFX (explosions, element-specific), particle effects, and a main menu.
- Add high-score persistence (simple file or SQLite) and pause screen.

Enjoy — tell me if you want me to generate starter art assets to match your style or to tweak specific gameplay values.
# Jet Shooter — Pygame + Arcade versions

Two versions of a small 2D endless shooter are included:

- `jet_shooter_pygame.py` — implemented with `pygame` (primary).
- `jet_shooter_arcade.py` — alternative implementation with `arcade`.

Concept
- Player has a gun and can switch between three elements: Air, Water, Fire.
- Each element has a different attack style and is more effective against a certain enemy tier.
- Enemies spawn endlessly: Beginner (3 HP), Mid (1 HP), Hard (2 HP + fires bombs).
- Player has 3 lives. Each kill = 5 points.

Run
1. Create a virtual env and install deps:

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1; pip install -r requirements.txt
```

2. Run the pygame version:

```powershell
python jet_shooter_pygame.py
```

Or run the arcade version:

```powershell
python jet_shooter_arcade.py
```

Notes
- Both scripts use simple procedural shapes so no external image assets are required.
- The UI is dark/techy: neon accents, HUD, and element indicators.

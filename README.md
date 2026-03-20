<p>
	<img alt="Python" src="https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" />
	<img alt="Pygame" src="https://img.shields.io/badge/Pygame-2.x-00A300?style=for-the-badge" />
	<img alt="Audio" src="https://img.shields.io/badge/Audio-pygame.mixer-6aa6ff?style=for-the-badge" />
	<img alt="Save System" src="https://img.shields.io/badge/Save%20System-pickle-ff7a59?style=for-the-badge" />
</p>

# <img src="images/Coins/coin.png" width="22" height="22" alt="" /> Battle Royale (Pygame)

A small 2D, gladiator-themed action game built with **Python** and **Pygame**.

You start in a prison cell, collect coins, visit the shop for upgrades, and fight through a sequence of arena battles. Between arenas you return to the hall, where you can save progress and prepare for the next fight.

## <img src="images/Coins/coin.png" width="18" height="18" alt="" /> Features

- Scene-based flow (Main Menu → Intro → Prison → Hall → Shop → Arena)
- Multiple enemy encounters (including projectile and poison mechanics)
- Shop upgrades (damage, health, shield, potions)
- Coin collection and score-based progression
- Music + sound effects via `pygame.mixer`
- Simple save/load using a local `save_game.pkl`

## <img src="images/Coins/coin.png" width="18" height="18" alt="" /> Requirements

- Python 3.8+ (3.10+ recommended)
- Pygame 2.x

## <img src="images/Coins/coin.png" width="18" height="18" alt="" /> Run the game

From the repository root (important so relative asset paths resolve):

```bash
python -m pip install pygame
python main.py
```

If you are using a virtual environment:

```bash
python -m venv .venv
\.venv\Scripts\activate
python -m pip install pygame
python main.py
```

## <img src="images/Coins/coin.png" width="18" height="18" alt="" /> Controls

### <img src="images/Coins/coin.png" width="16" height="16" alt="" /> Player controls

- **A / D** — Move left / right
- **W** — Jump
- **E** — Attack (combat) / Buy item (shop)
- **SPACE (hold)** — Block with shield (only after you buy a shield upgrade)

### <img src="images/Coins/coin.png" width="16" height="16" alt="" /> Navigation / scenes

- **ESC** — Return to main menu (from most scenes)
- **SPACE** — Skip intro / arena intro
- **1** — Leave the prison (Prison → Hall)
- **2** — Go to the shop (Hall → Shop)
- **3** — Go to the arena (Hall → Arena)
- **4** — Continue after winning an arena (when prompted)
- **B** — Go back (e.g., Hall ↔ Prison / Shop → Hall)

### <img src="images/Coins/coin.png" width="16" height="16" alt="" /> Mouse

- **Left click** — Menu buttons (Start / Quit)
- **Left click** — Save/Load icons when they are visible

## <img src="images/Coins/coin.png" width="18" height="18" alt="" /> Saving and loading

The game includes a lightweight save system:

- **Save**: click the **Save** button in the hall scenes.
- **Load**: click the **Load** button during arena fights (when available).

Saves are stored in `save_game.pkl` in the repo root.

Notes:

- If you run into load errors (or want to reset progress), delete `save_game.pkl` and start a new game.
- Save data is created with Python `pickle`, so it is not intended to be edited manually.

## <img src="images/Coins/coin.png" width="18" height="18" alt="" /> Project structure

- `main.py` — Entry point; level setup; game loop; save/load helpers
- `scene.py` — Scene/state machine (menu, intros, prison/hall/shop/arena flow)
- `engine.py` — Core systems (input, physics, camera, combat/conditions, shop)
- `utilities.py` — Entity factory helpers, UI text/surfaces, shared assets
- `button.py` / `menu.py` — UI button implementations
- `level.py` — Level container + save/load buttons
- `soundmanager.py` — Audio + music registry
- `images/` — Sprites and backgrounds
- `sounds/` — Sound effects and music

## <img src="images/Coins/coin.png" width="18" height="18" alt="" /> Troubleshooting

- **Black window / missing files**: run with the working directory set to the repo root (asset paths like `images/...` are relative).
- **No audio**: make sure your system audio is available; the game initializes `pygame.mixer` on startup.
- **Load errors**: delete `save_game.pkl` to reset progress.

## <img src="images/Coins/coin.png" width="18" height="18" alt="" /> Contributing

Issues and pull requests are welcome.

If you plan to contribute:

- Keep changes focused and easy to review.
- Avoid committing local folders like `.venv/`, `.idea/`, and `__pycache__/`.

## <img src="images/Coins/coin.png" width="18" height="18" alt="" /> License

No license file is currently included. If you plan to publish this publicly, consider adding a LICENSE (e.g., MIT) and clarifying the licensing/attribution for art and audio assets.

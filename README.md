# HERO GUARDIAN 2.0

This game is built in Godot Engine 4 using GDscript on Mobile. It is under development. 

A 2D pixel-art platformer where a knight runs, jumps and double-tap sprints through a sunny level, dodging patrolling slimes and collecting coins.

<!-- Add a gameplay screenshot here, e.g. ![Gameplay](screenshots/gameplay.png) -->

## About

Hero Guardian 2.0 is a small platformer built solo in **Godot 4.7** (Mobile renderer), written entirely on a phone. It has touch controls on screen, so it plays natively on Android, and keyboard controls for desktop testing.

The level is built around simple, readable mechanics: patrol enemies, moving platforms, pits that kill you, and 40 coins scattered around.

## Features

- Knight character with idle, walk, run, jump and fall animations
- **Double-tap run:** tap left or right twice quickly to sprint (250 speed vs. 100 for walking)
- Slime enemies that patrol back and forth, turning around with raycasts when they hit a wall
- Moving platforms (animated with `AnimationPlayer`)
- 40 collectible coins with a pooled sound system (so rapid pickups don't cut each other off)
- Death zones with a slow-motion death, then an automatic level restart
- Parallax sky background and background music
- On-screen touch buttons (left, right, jump)

## Controls

| Action | Touch | Keyboard |
|--------|-------|----------|
| Move left / right | Left / Right buttons | Arrow keys |
| Jump | Jump button | Space / Enter |
| Run | Double-tap a direction button | Double-tap an arrow key |

## Getting Started

### Requirements

- [Godot 4.7](https://godotengine.org/download) (the project is configured for 4.7, Mobile renderer)

### Run it

1. Clone the repo:
   ```
   git clone https://github.com/USERNAME/REPO.git
   ```
2. Open Godot, click **Import**, and pick `project.godot` inside the `hero-guardian` folder.
3. Press **F5** to play. The main scene is `game.tscn`.

### Export to Android

1. Install the Android export templates and set up the Android SDK in Godot.
2. Go to **Project > Export**. An Android preset is already included (arm64-v8a).
3. Set your own export path and package name (the default is `com.example.$genname`), then export an APK.

## Project Structure

```
hero-guardian/
├── game.tscn          # Level 1 (main scene)
├── Scenes/            # Player (mc.tscn, mc.gd), music
├── Scripts/           # Slime AI
├── Slime.tscn         # Patrolling enemy
├── coin.tscn          # Collectible coin
├── Platform.tscn      # Moving platform
├── Tile.tscn          # Tilemap
├── killzone.tscn      # Death zone
├── Buttons.tscn       # Touch controls
├── node.gd            # SFX autoload (pooled sound player)
├── individual_sheets/ # Hero sprites
├── Skyboxes/          # Background sky images
├── brackeys_platformer_assets/  # Tileset, coin, slime, sounds, music
└── addons/admob/      # AdMob plugin (installed, not active in gameplay yet)
```

## Development Notes

- Developed entirely on a mobile device.
- Autoloads: `SFX` (sound pool) and `Music`.
- The AdMob plugin is installed and an interstitial ad call exists in `killzone.gd`, but it is commented out, so the game currently shows no ads.

## Roadmap

- [ ] Win condition when all 40 coins are collected (the level says "collect all coins to win but doesn't handle win condition")
- [ ] Combat (the hero has attack animations that aren't wired up yet)
- [ ] More levels
- [ ] Title screen and menus
- [ ] Coin counter on screen
- [ ] Ads and monetization, once asset licenses allow it (see below)

## Credits

- Code and design: Niq
- Hero sprites: Ozzbit Games (free version)
- Tileset, coin, slime, platform sprites: analogStudios_ and RottingPixels, repackaged by [Brackeys](https://brackeys.com) (CC0)
- Sound effects and music: Brackeys, Asbjørn Thirslund and Sofia Thirslund (CC0)
- Sky backgrounds: [Kenney](https://kenney.nl) (CC0)
- Touch button UI: QOG-STUDIO
- AdMob plugin: Poing Studios (MIT)
- Engine: [Godot](https://godotengine.org)

## License

Code license:

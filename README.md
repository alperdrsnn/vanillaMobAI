# VanillaMobAI

Vanilla Bedrock–style mob AI for PocketMine-MP.

![Version](https://img.shields.io/badge/version-1.3.0-blue)
![PocketMine-MP](https://img.shields.io/badge/PocketMine--MP-5.0%2B-orange)
[![](https://poggit.pmmp.io/shield.state/VanillaMobAI)](https://poggit.pmmp.io/p/VanillaMobAI)
<a href="https://poggit.pmmp.io/p/VanillaMobAI"><img src="https://poggit.pmmp.io/shield.state/VanillaMobAI"></a>

---

## About

VanillaMobAI gives PMMP mobs vanilla-like behavior: wandering, combat, breeding, natural spawning, and interactions such as milking and shearing. Balance values (damage, speed, breeding timers) follow vanilla references in code and are **not** exposed in config.

The plugin is **stable and ready for production use** on PocketMine-MP servers. Development is ongoing — new mobs and behaviors will continue to be added, but the current feature set is fully usable today.

---

## Features

- Goal-based AI (wander, panic, tempt, attack, creeper explosion)
- Line of sight — no seeing through walls
- Creative players are not targeted by hostiles
- Natural spawning (caps, light, distance, world filters)
- Spawn eggs + monster spawner support (set spawner type with an egg)
- Horses: taming, saddle, armor, riding, breeding
- Breeding, milking, shearing, dyeing, chicken eggs
- Performance: activation range, tick budget, async pathfinding

---

## Mobs

| Mob | Type |
|-----|------|
| Cow, Pig, Sheep, Chicken, Horse | Passive |
| Zombie, Skeleton, Spider, Creeper | Hostile |

---

## Installation

1. Place the `VanillaMobAI` folder in `plugins/`.
2. Start the server.
3. Edit `plugin_data/VanillaMobAI/config.yml`.

**Requirements:** PocketMine-MP 5.0.0+, PHP 8.1+

---

## Configuration

Server settings live in `config.yml`. Example:

```yaml
features:
  natural-spawn: true
  mob-ai: true
  monster-spawners: true

worlds:
  natural-spawn-mode: whitelist
  natural-spawn-whitelist:
    - world

natural-spawn:
  passive-cap: 12
  hostile-cap: 24
  mobs:
    creeper: false
```

**Whitelist:** Natural spawn only in listed world folder names.  
**Blacklist:** Spawn everywhere except listed worlds (default: nether, end).

Performance tuning is under the `performance` section. Gameplay balance (damage, speed, etc.) is intentionally not configurable.

---

## Commands

| Command | Description |
|---------|-------------|
| `/mobai stats` | AI and performance summary |
| `/mobai reload` | Reload config (spawn settings) |

Permission: `vanillaMobAI.command` (default: op)

---

## Roadmap

- [ ] More vanilla mobs
- [ ] Biome-based spawn weights
- [ ] Additional vanilla interactions

Use GitHub Issues for bugs and suggestions.

---

## License

MIT — see `LICENSE` for details.

**Author:** grinn34

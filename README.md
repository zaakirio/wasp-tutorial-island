# WaspTutorial - Tutorial Island Completer

A standalone Simba script that automatically completes OSRS Tutorial Island using the WaspQuests framework. Designed with human-like behavior patterns and efficiency techniques sourced from the [WaspScripts tutorials](https://waspscripts.com/tutorials).

## Requirements

- **Simba** with SRL-T, WaspLib, and WaspQuests installed
- **RuneLite** in fixed classic layout with the WaspScripts profile active
- Start the script **after character creation** is complete
- Player must have already talked to Gielinor Guide and opened the settings tab
- Simba must be targeted to the RuneLite/OSRS client window

## What It Does

Completes the entire Tutorial Island sequence automatically:

| Section | Skills Covered |
|---------|---------------|
| Gielinor Guide | Settings verification, initial dialogue |
| Survival Expert | Fishing, Cooking, Woodcutting, Firemaking |
| Master Chef | Bread making (dough + range) |
| Quest Guide | Quest tab introduction |
| Mining Instructor | Mining (tin/copper), Smelting, Smithing |
| Combat Instructor | Melee combat, Equipment, Ranged combat |
| Account Guide | Banking, Poll booth |
| Brother Brace | Prayer, Friends list |
| Magic Instructor | Magic tab, Wind Strike spell |

After completion, the player is teleported to Lumbridge with a post-tutorial settings check.

## Features

### Human-Like Behavior
- **Randomized delays** with weighted distributions (short pauses more common than long ones)
- **Camera jitter** between sections with human-like imprecision
- **Antiban micro-actions** — random tab toggles, mouse movements, POV changes
- **Section transitions** with natural pauses and varied idle behaviors
- **BioHash-driven randomness** for per-account behavioral fingerprinting

### Efficiency Techniques (from WaspScripts Tutorials)

The following techniques from the [WaspScripts tutorial library](https://waspscripts.com/tutorials) are implemented:

| Tutorial | Technique | Implementation |
|----------|-----------|----------------|
| [Lape Syntax](https://waspscripts.com/tutorials/lape-syntax-by-torwent) | Named constants | All coordinates, timeouts, retry limits, and probability thresholds extracted to `const` block |
| [Caching](https://waspscripts.com/tutorials/caching-by-torwent) | Position caching | `GetCachedPosition()` avoids redundant `Map.Position` calls (100-150ms each) with a 500ms TTL |
| [Caching](https://waspscripts.com/tutorials/caching-by-torwent) | Tick count timing | `GetTickCount` cached at section start for elapsed time tracking |
| [Debugging](https://waspscripts.com/tutorials/debugging-by-torwent) | Progress logging | `LogSection()` and `LogStep()` print timestamped progress to console |
| [Walker and Doors](https://waspscripts.com/tutorials/walker-and-doors-by-bootje) | Door handler | `Map.Walker._DoorHandler.Enabled := True` for reliable door traversal |
| [Basic Script](https://waspscripts.com/tutorials/basic-script-by-torwent) | WaitUntil pattern | All item/interface waits use `WaitUntil` with timeouts |
| [Compiler Directives](https://waspscripts.com/tutorials/compiler-directives-by-torwent) | Conditional includes | `{$IFNDEF}` guards prevent duplicate includes |
| [Overriding](https://waspscripts.com/tutorials/overriding-by-torwent) | Custom step handlers | Quest framework extended with custom completion callbacks |
| [TPoints](https://waspscripts.com/tutorials/tpoints-by-torwent) | TPA/ATPA patterns | NPC detection in `CastWindStrikeOnChicken` uses clustered point arrays |

### Retry Logic
- **Cooking** retries up to 3 times if shrimps fail to cook
- **Wind Strike** retries up to 7 times with spell re-selection
- All retry functions log warnings on failure

### Console Output

The script logs structured progress to the Simba output panel:

```
[Tutorial] ========================================
[Tutorial] WaspTutorial - Tutorial Island Completer
[Tutorial] ========================================
[Tutorial] === Gielinor Guide (Start) === (0s elapsed)
[Tutorial]   > Running pre-tutorial settings verification
[Tutorial]   > Opening inventory tab
[Tutorial]   > Waiting for shrimps then opening stats
[Tutorial] Previous section completed in 45230ms
[Tutorial] === Master Chef (Bread Making) === (47s elapsed)
...
[Tutorial] ========================================
[Tutorial] Tutorial Island completed in 482 seconds
[Tutorial] ========================================
```

## Usage

1. Open Simba and load `wasptutorial.simba`
2. Target the RuneLite client window using Simba's crosshair selector
3. Log in and complete character creation
4. Talk to Gielinor Guide and open the settings tab
5. Press the green play button in Simba

The script creates a **non-ironman account** by default.

## Configuration

Key constants at the top of the script can be adjusted:

| Constant | Default | Description |
|----------|---------|-------------|
| `POSITION_CACHE_TTL` | 500ms | How long to cache `Map.Position` results |
| `WAIT_ITEM_TIMEOUT` | 12000ms | Max wait for inventory items to appear |
| `MAX_COOK_RETRIES` | 3 | Retry attempts for cooking shrimps |
| `MAX_SPELL_RETRIES` | 7 | Retry attempts for Wind Strike |
| `CAMERA_JITTER_CHANCE` | 0.35 | Probability of random camera rotation |
| `TAB_CHECK_CHANCE` | 0.15 | Probability of idle tab toggle |

## Dependencies

- [SRL-T](https://github.com/Torwent/SRL-T) — Simba Resource Library
- [WaspLib](https://github.com/Torwent/WaspLib) — Extended botting utilities
- [WaspQuests](https://github.com/Torwent/WaspQuests) — Quest solving framework

## Project Structure

```
wasp-tutorial-island/
  wasptutorial.simba   # Main script (single file)
  README.md            # This file
```

## Credits

Built on the [WaspScripts](https://waspscripts.com) ecosystem by Torwent and contributors. Tutorial efficiency techniques sourced from the community tutorial library.

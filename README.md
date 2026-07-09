# Erudite-Divination
A full scale 
Erudite Divination is a Dalamud plugin featuring a divination toolkit for FFXIV tarot readings, rune casting, and an immersive roleplay experience of doing or experiencing a divination for or by your characters.

The plugin is intended as a local/social divination table: tarot cards, casting charms, reader guidance, and observer-facing board state. It is not a physical gameplay tool but instead a window. It does not automate combat or gathering, read encounter state, modify memory, use packets, or interact with FFXIV systems beyond normal Dalamud plugin UI.

## Current State

The plugin currently has a basic local dev skeleton:

- `/divination` opens and closes the main window.
- `/tarot` still works as a temporary fallback command.
- The main window is movable and uses Dalamud windowing.
- The first mock table layout is drawn with ImGui placeholder colors and shapes.
- Reader and Observer preview states are separated visually.
- The reader side shows private journal-style guidance placeholders.
- The observer side shows public board-state placeholders.

Deck logic, charm casting, image assets, shared observer behavior, and saved readings are not implemented in the plugin yet.

## Design Direction

The final tool is meant to feel like a portable heirloom divination set rather than a modern utility window: walnut case, midnight velvet, brass fittings, cards, journal, candlelight, charms, and quiet serif labels.

Images should be treated as first-class UI assets. Future work should use organized PNG assets, Dalamud texture loading, and ImGui image drawing rather than relying only on hardcoded rectangles.

## Local Development

Build from the repository root:

```powershell
dotnet build
```

The project expects Dalamud development DLLs to be available through XIVLauncher at:

```text
%AppData%\XIVLauncher\addon\Hooks\dev
```

This project should be tested as a local dev plugin first. Do not add it to a custom plugin repository until the local version is stable.

## Safety Boundary

Erudite Divination should remain a roleplay interface only. It should not:

- automate gameplay
- inspect combat, encounter, or player state for decisions
- modify game memory
- send or intercept packets
- perform hidden actions on behalf of the player

The reader controls the table. Observers should be able to witness public board state without gaining access to reader-private guidance or controls.

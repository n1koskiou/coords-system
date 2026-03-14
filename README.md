# CoordsPlugin — README

## Overview
A lightweight RocketMod plugin for Unturned that adds a `/coords` command showing the player's current XYZ position in chat. Admin-only by default via permissions.

---

## Commands

| Command | Aliases | Description | Permission |
|---|---|---|---|
| `/coords` | `/pos`, `/position`, `/location` | Shows your current X, Y, Z coordinates | `coords.use` |

**Example output:**
```
[Coords] X: 1024.3  Y: 45.0  Z: -873.6
```

---

## Installation

1. Build the plugin: `dotnet build -c Release` inside the `CoordsPlugin` folder
2. Copy `CoordsPlugin.dll` to your server at:
```
U3DS\Rocket\Plugins\CoordsPlugin.dll
```
3. Restart the server — no config file is generated, the plugin is ready immediately.

---

## Permissions

Open `U3DS\Rocket\Permissions.config.xml` and add the permission to whichever group should have access. To make it **admin-only**, add it only to your admin group and leave it out of the default player group.

**Admin group only:**
```xml
<Group>
  <Id>admin</Id>
  <Permissions>
    <Permission Cooldown="0">coords.use</Permission>
  </Permissions>
</Group>
```

**All players:**
```xml
<Group>
  <Id>default</Id>
  <Permissions>
    <Permission Cooldown="0">coords.use</Permission>
  </Permissions>
</Group>
```

---

## Coordinate System

Unturned uses Unity's coordinate system:

- **X** — East/West position
- **Y** — Altitude (height above sea level)
- **Z** — North/South position

Coordinates are displayed with 1 decimal place of precision.


# xBarterHouse

**xBarterHouse** is a premium barter-style auction house plugin for Paper/Spigot 1.20–1.21+.  
Players can list items from their hand and trade them for other materials — no economy required.

---

## Features

- **Item-for-item barter** — list any item and set a price in materials (e.g. 16 diamonds). No virtual economy needed.
- **GUI marketplace** — 54-slot main menu with automatic listing slots, border decoration, and navigation buttons.
- **My Listings & Expired Items** — sub-menus to manage your active listings or reclaim unsold/expired items.
- **Flat-file storage** — all data saved to `data.yml` inside the plugin folder. No MySQL, no database setup.
- **Offline delivery** — if the seller is offline when a trade completes, the items are delivered on their next login via `PlayerJoinEvent`.
- **Fully translatable** — every single message, title, button name, and lore line is loaded from `config.yml`. Zero hardcoded strings in the source code.
- **Smart tab completion** — `/ah` suggests subcommands, valid amounts (1, 16, 32, 64), and every available `Material` name.
- **Hex color support** — use `&#RRGGBB` notation anywhere in config for custom RGB colors.
- **No italic glitch** — all item lore and display names have forced `ITALIC: false` decoration, keeping fonts sharp and clean.
- **No external dependencies** — standalone build with shaded Adventure library. Just drop and play.

---

## Installation

1. Download the latest `xBarterHouse-1.0.0.jar` from the releases page.
2. Place the jar file into your server's `plugins/` directory.
3. Restart your server or run `/reload` (restart recommended).
4. A default `config.yml` and empty `data.yml` will be generated automatically.
5. Edit `plugins/xBarterHouse/config.yml` to customise messages, colors, and GUI settings to your liking.
6. Type `/ah` in-game to open the barter market.



## Requirements

- **Java 17+**
- **Paper 1.20+** (or any compatible Spigot fork with Adventure API)
- **No other plugins required**

---

## Configuration

All messages, GUI titles, button names, lore lines, and market tags are defined in `config.yml`.  
Use `&` for legacy Minecraft color codes or `&#RRGGBB` for hex/RGB colors.  
The placeholder `%prefix%` is automatically replaced with the configured prefix.

### Example `config.yml`

```yaml
prefix: "&b&lxBarterHouse &8» "

messages:
  item-listed: "%prefix%&7Your item has been listed for &e%amount%x %material%&7!"
  trade-success: "%prefix%&aTRADE COMPLETE! &7You received your requested items."
  trade-received: "%prefix%&aYou received items from a completed barter trade!"
  no-permission: "%prefix%&cYou do not have permission to use this market!"
  invalid-price: "%prefix%&cInvalid syntax! Use: &e/ah sell <amount> <material>"
  invalid-material: "%prefix%&cThe specified material does not exist!"
  air-hand: "%prefix%&cYou cannot sell air! Hold an item in your hand."
  not-enough-items: "%prefix%&cYou do not have enough &e%amount%x %material%&c!"
  listing-cancelled: "%prefix%&7Your listing has been cancelled and item returned."
  item-returned: "%prefix%&7Your item has been returned to you."
  listings-title: "     &8» BARTER AUCTION HOUSE «"
  my-listings-title: "     &8» YOUR LISTINGS «"
  expired-title: "     &8» RECLAIM ITEMS «"
  no-listings: "&7You have no active listings."
  no-expired: "&7You have no items to reclaim."
  full-inventory: "%prefix%&cYour inventory is full! Items dropped on ground."
  help-menu:
    - "&8&m----------------------------------------"
    - "  &b&lBARTERHOUSE COMMANDS"
    - ""
    - "  &b/ah &8- &7Open the barter auction house GUI."
    - "  &b/ah sell <amount> <material> &8- &7List your held item."
    - "  &b/ah help &8- &7Show this help menu."
    - "&8&m----------------------------------------"

gui-settings:
  border-item: "GRAY_STAINED_GLASS_PANE"

  expired-orders:
    material: "POISONOUS_POTATO"
    name: "&c&lEXPIRED LISTINGS"
    lore:
      - "&7Click to reclaim your"
      - "&7unsold or expired market items."
    slot: 48

  my-listings:
    material: "BOOK"
    name: "&b&lYOUR ACTIVE LISTINGS"
    lore:
      - "&7Click to manage items you"
      - "&7currently have up for barter."
    slot: 50

  author-info:
    material: "PLAYER_HEAD"
    name: "&#FF6B9D&lPLUGIN &f&lBY &#00D4FF&lEMIRLQQ1"
    lore:
      - "&#2A2A2A&m------------------------------"
      - "  &#FF5555&lVERSION 1.0.0"
      - "&#2A2A2A&m------------------------------"
    slot: 49

market-tags:
  separator: "&8--------------------------------"
  info-title: "&e&lTRADE INFORMATION:"
  seller: "&7▶ Seller: &f%seller%"
  demanded-price-format: "&7▶ Cost to Buy: &b%amount%x &e%material%"
  separator-2: "&8--------------------------------"
  click-to-trade: "&a&l[!] CLICK TO ACCEPT THIS TRADE"
  click-to-cancel: "&c&l[!] CLICK TO CANCEL YOUR LISTING"
```

---

## File structure

```
plugins/xBarterHouse/
  ├── config.yml          # All messages, GUI settings, market tags
  ├── data.yml        

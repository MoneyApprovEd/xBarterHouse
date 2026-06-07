# xBarterHouse

**xBarterHouse** is a premium barter-style auction house plugin for Paper/Spigot 1.20–1.21+.  
Players can list items from their hand and trade them for other materials — no economy required.

## Features

- **Item-for-item barter** — list any item and set a price in materials (e.g. 16 diamonds)
- **GUI marketplace** — 54-slot main menu with paginated listings, expired reclaim, and listing management
- **Flat-file storage** — `data.yml`, no database needed
- **Offline delivery** — trade items are delivered on next login via `PlayerJoinEvent`
- **Fully translatable** — all text is in `config.yml`, zero hardcoded strings
- **Tab completion** — `/ah` suggests `sat`, `yardim`, amounts, and material names
- **Hex color support** — use `&#RRGGBB` in config for custom colors
- **No external dependencies** — standalone, shaded build

## Commands

| Command | Description |
|---------|-------------|
| `/ah` | Open the barter market GUI |
| `/ah sat <miktar> <materyal>` | List the item in your hand (Turkish: `sat`, English `sell` also works) |
| `/ah yardim` | Show the help menu (Turkish: `yardim`, English `help` also works) |

## Permissions

All permissions were removed in v1.0.0 — every player can use the market by default.

## Configuration

All messages, GUI titles, button names, and market tags are in `config.yml`.  
Use `&` for legacy colors or `&#RRGGBB` for hex colors.

### Example `config.yml` structure

```yaml
prefix: "&b&lxBarterHouse &8» "

messages:
  item-listed: "%prefix%&7Eşyanız başarıyla listelendi! İstenen: &e%amount%x %material%"
  listings-title: "     &8» ᴛᴀᴋᴀs ᴘᴀᴢᴀʀɪ «"

gui-settings:
  expired-orders:
    material: "POISONOUS_POTATO"
    name: "&c&lsᴜʀᴇsɪ ᴅᴏʟᴀɴʟᴀʀ"
  my-listings:
    material: "BOOK"
    name: "&b&lᴀᴋᴛɪғ ɪʟᴀɴʟᴀʀɪᴍ"

market-tags:
  seller: "&7▶ Satıcı: &f%seller%"
  click-to-trade: "&a&l[!] ᴛᴀᴋᴀsɪ ᴋᴀʙᴜʟ ᴇᴛ"
  click-to-cancel: "&c&l[!] ɪʟᴀɴɪ ɪᴘᴛᴀʟ ᴇᴛ"
```

## Installation

1. Drop `xBarterHouse-1.0.0.jar` into your server's `plugins/` folder.
2. Restart or `/reload` the server.
3. Edit `plugins/xBarterHouse/config.yml` to customise messages.
4. Use `/ah` to open the market.

## Building from source

```bash
git clone https://github.com/EMIRLQQ1/xBarterHouse.git
cd xBarterHouse
mvn clean package
```

The compiled jar will be at `target/xBarterHouse-1.0.0.jar`.

## Requirements

- **Java 17+**
- **Paper 1.20+** (or compatible Spigot fork)
- No other plugins required

## License

MIT — see [LICENSE](LICENSE) (if included) for details.

## Author

**EMIRLQQ1** — Made with ❤

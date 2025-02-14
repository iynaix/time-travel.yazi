# time-travel.yazi

A Yazi plugin for browsing backwards and forwards in time via BTRFS / ZFS
snapshots.

https://github.com/user-attachments/assets/6d2fc9e7-f86e-4444-aab6-4e11e51e8b34

## Installation

```sh
ya pack -a iynaix/time-travel
```

> [!NOTE]
> The minimum required yazi version is 25.2.7.

## Usage

Add keymaps similar to the following to your `~/.config/yazi/keymap.toml`:

```toml
[[manager.prepend_keymap]]
on = ["z", "h"]
run = "plugin time-travel --args=prev"
desc = "Go to previous snapshot"

[[manager.prepend_keymap]]
on = ["z", "l"]
run = "plugin time-travel --args=next"
desc = "Go to next snapshot"

[[manager.prepend_keymap]]
on = ["z", "e"]
run = "plugin time-travel --args=exit"
desc = "Exit browsing snapshots"
```

#### Note for BTRFS

`sudo` is required to run btrfs commands such as `btrfs subvolume list`, the
plugin will drop into a terminal to prompt for the password.

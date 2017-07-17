# Tournament Management Commands

The following chat commands are provided for remote management of multiplayer tournament rooms:

- `!mp make <name>` - Creates a tournament room with the specified name.
  - This room is special in that it is not closed when all players have left the room, and it is password protected from players joining this room themselves.
  - When the match is finished, use `!mp close` to close the room.
- `!mp invite <username>` - Invites a player to the room.
  - Note that this does _not_ bypass any private message blocks available in the osu! client, so your tournament staff will need to tell players to disable "Block private messages from non-friends" in the osu! options.
- `!mp lock` - Locks the room so that players can’t change their team and slot.
- `!mp unlock` - Reverses the above.
- `!mp size <size>` - Sets the amount of available slots (1-16) in the room.
- `!mp set <teammode> [<scoremode>] [<size>]` - Sets various room properties.
  - `teammode` - 0: Head To Head, 1: Tag Coop, 2: Team Vs, 3: Tag Team Vs
  - `scoremode` - 0: Score, 1: Accuracy, 2: Combo, 3: Score V2
- `!mp move <username> <slot>` - Moves a player within the room to the specified 1-indexed slot.
- `!mp host <username>` - Transfers host to the player.
- `!mp clearhost` - Clears match host.
- `!mp settings` - Displays full match details.
- `!mp start [<time>]` - Starts the match after a set time (in seconds) or instantaneously if time is not present.
- `!mp abort` - Aborts the match.
- `!mp team <username> <colour>` - Moves a player to the specified team.
  - `colour` - red, blue
- `!mp map <mapid> [<playmode>]` - Changes the beatmap and playmode of the room.
  - `playmode` - 0: osu!, 1: Taiko, 2: Catch The Beat, 3: osu!Mania
- `!mp mods <mod> [<mod>] [<mod>] …` - Removes all currently applied mods and applies these mods to the room.
  - Any amount of mods can be entered.
  - `mod` - HR, DT, FL, HD, FI, Freemod, None
- `!mp timer [<time>]` - Begins a countdown timer.
  - `time` is 30s default.
  - Timer announcements occur every minute, 30s, 10s, 5s and earlier.
- `!mp aborttimer` - Stops the current timer (both normal timers and match start timer)
- `!mp kick <username>` - Kicks the player from the room.
- `!mp password [<password>]` - Changes the password of the room. The password will be removed if `<password>` is not provided.
- `!mp close` - Closes the room.

Sending `!mp help` to BanchoBot will reveal the commands.

`#<userid>` may substitute `<username>` in all of the commands. Usernames must have any whitespace be replaced with underscores ( `_` ).

## Usage

The commands are usable from both within osu! or through an IRC client such as mIRC, HexChat, or HydraIRC.

The original host of a multiplayer room can also use these commands. If the original host leaves, the next host will not inherit the commands. The original host will be again be able to use the commands if they rejoin the room.

## Example usage

The following is an example of command usage:

- `!mp invite Zallius` - Invite Zallius to the room.
- `!mp move Loctav 4` - Move Loctav to slot 4 of the room.
- `!mp team Zallius blue` - Move Zallius to the blue team.
- `!mp team Loctav red` - Move Loctav to the red team.
- `!mp set 0 2` - Set the team mode to Head To Head and scoring mode to Combo.
- `!mp start` - Start the match instantaneously.
# red13game
Red13 - The Life Of A Blue Zone Runner

Choose Red13 or Rapture before a run. Move with WASD or arrow keys and restart
with R. Rapture can hold Space or the on-screen Shoot button to fire at the
Sweaty Try Hard. It crosses at 100 pixels per second in phase 5 for Rapture and from phase 10 for both characters; each hit
slows it to 40 pixels per second for two seconds, and three hits defeat it.
Defeated enemies drop a 5 GCoin pickup. Red13 earns 3 saved GCoin for each complete crossing he survives.
The selected character is remembered in this browser.

Rapture's reference-based sprite and generation prompt are documented in
[ARTWORK.md](ARTWORK.md). The website serves the game from its `red13/` folder;
game changes must also be copied there.

Jammer Packs replace normal scheduled drone loot with an independent 5% chance
per eligible drop. A full seven-item loot pool does not roll; occupied points
are excluded before selecting a location. Each roll creates exactly one item.
Enemy GCoin rewards and cosmetic crate rewards are not eligible.

Configure `jammerSpawnChance` (0–1), `jammerProtectionMs` (default 20,000) and
`debugLootRolls` in `js/loot-config.js`, and copy changes into the website's
`red13/js/loot-config.js`. Debug console messages report the chance, value,
location and success/failure for each roll. Increment the script URL version in
both HTML files when publishing config changes so browsers load the update.

Collect the teal J pickup to block blue-zone damage temporarily. The HUD shows
remaining seconds. Red zones and enemies still hurt. Another pickup refreshes
the timer without stacking durations; restarting clears protection.

Rolls use `crypto.getRandomValues` with fresh OS/browser entropy, without stored
seeds, failure counters or guaranteed drops. Reloads and hosting restarts do not
change the configured chance. Each browser player has its own loot and timer;
Red13 has no shared multiplayer game server. A future shared-world mode would
need to perform the roll once on its authoritative server, not once per client.

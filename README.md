# 3D Shooter

A first-person shooter that runs in the browser, written with three.js.

## Play it in Google Chrome

1. Download `shooter-standalone.html` (open it on GitHub and use **Download raw file**, or clone the repo).
2. Double-click it, or drag it into a Chrome window. It needs no internet connection and no server.
3. Click **Survival** or **Free Play**. Chrome captures the mouse when the game starts; press `Esc` to release it.

`shooter.html` is the same game but loads three.js from a CDN, so it needs a connection.

## Play online with friends

The host picks a mode before pressing Start: **Deathmatch** (free for all, the original) or **Co-op: fight the enemies together**, where everyone is on the same team against waves of soldiers. In co-op the host runs the enemies and everyone sees and shoots the same ones; enemy bullets hurt everyone, there is no friendly fire, and each player scores the kills they make. Waves get bigger with more players.

Up to 4 players, free-for-all on the full 220 m field (shoot, build, loot chests; most eliminations wins). It uses peer-to-peer WebRTC, so there is no server and no account. You swap two short codes in any chat app:

1. **Host:** click **Play Online**, then **Create game code**. A number code (8 digits) appears. Tell it to your friends.
2. **Friend:** click **Play Online**, type the host's code under **Join** and press **Join**. They are in. (The old copy and paste codes are still there under "use copy and paste codes instead".) The number codes pass through the shared database on the published page and a public relay (ntfy.sh), so you need an internet connection.
3. **Host:** paste the reply under **Connect friend**. Repeat steps 1-3 for each extra friend, then click **Start match**.
4. **Friends:** click **Join match** when the host has started.

Use the downloaded `shooter-standalone.html` for online play. Everyone should open the same version of the file. If a friend cannot connect (strict corporate or mobile networks can block peer-to-peer), try a different network.

## Profile

On the main menu, click the round picture to upload a profile picture and type a name (up to 12 characters). They are saved in your browser, shown next to your health bar, and shown to friends online (name tag above your head and on the scoreboard). The picture is cropped and shrunk to 96x96 and never leaves your computer except to friends you connect to.

**Passwords:** click "Set a password for this name" under your name to claim it. Anyone else who types that name has to enter the password first (three wrong tries put them back on their old name). Passwords are stored only as salted PBKDF2 hashes, in the shared database when the page has one (so the claim follows the name everywhere) or in your browser otherwise. The check is done by the page itself, so it keeps other players off your name but is not bank-grade security.

**Sign in:** the game asks you to sign in or create an account (a username and a password) when you open it (not on a Mac, where it stays out of your way and you use the Sign in button when you want it), or you can play as a guest. Your points, shop items, skins and picture are saved to your account (in the shared database on the published page, so they follow you to any device; otherwise in this browser) and come back whenever you sign in. A guest's points and items are merged into the account you sign in to. Use "Sign out" under your name to switch accounts. The built-in "brnloz owner" account also turns on the admin tools (backtick panel and hotkeys) for Breno.

## Leaderboard

The **Leaderboard** button on the main menu shows the best Survival score, Free Play score and Arena kill count. Bests are saved in your browser (per profile name). On the published Claude page they are also saved to a shared database, so the board lists everyone who plays that page (it needs a signed-in viewer with Contributor access to write).

## Maps

Pick a map on the main menu: **Meadow** (the original), **Dustbowl** (desert with cacti and ruins), **Frostbite** (snow, ice blocks and drifts), **Moonlight** (night with stars and street lamps) **Scrapyard** (overcast, lots of containers, silos and wrecks), **Overgrowth** (jungle with mossy ruins), **Ashfall** (volcanic rock and lava pools), **Downtown** (city blocks with tall buildings) and **Golden Hour** (a red-gold sunset desert). Your choice is remembered. Online, the host's map is used for everyone.

## Guns

Open **Armory** on the main menu to see every gun with a picture, its stats and where to get it (exclusives show whether you own them).

29 guns found in chests (the better the chest, the rarer the gun), several with their own mechanics. Common: Pistol (you start with it), SMG, Machine Pistol, Nail Gun, Sawed-Off. Rare: Assault Rifle, Shotgun, Revolver, Double Barrel, Hand Cannon, Bullpup Rifle, **Flamethrower** (a cone of fire that sets enemies burning), **Ricochet Gun** (bullets bounce off walls). Epic: Sniper Rifle, Marksman Rifle, Light Machine Gun, Crossbow, Auto Shotgun, Plasma Rifle, **Arc Caster** (lightning chains to 3 more enemies), **Piercing Lancer** (goes through every enemy in line), **Grapple Gun** (hook a surface and swing yourself to it, or yank an enemy to you). Legendary: Rocket Launcher, Grenade Launcher, Railgun, Minigun, Anti-Material Rifle, Rocket Pod, **Mine Launcher** (sticky proximity mines), **Charge Rifle** (hold fire to charge, release to shoot). `Ctrl` + `V` `V` `A` gives you all of them.

A hundred and three **exclusive guns** are not in chests: Gilded Revolver, Void Cannon, Storm Rifle, Dragon's Breath, **Blink Pistol** (teleports you to where you shoot), **Leech SMG** (heals you on every hit), **Singularity** (a black hole that drags enemies together, then explodes) **Sentry Kit** (drops an auto-firing turret), **Hornet Hive** (3 attack drones circle you and shoot for 14s), **Chrono Cannon** (a time field that slows enemies to a crawl), **Skyfall Designator** (paint a spot, an orbital beam hits 2s later), **Aegis Projector** (a dome that heals you and eats enemy bullets), **Stormcaller** (a storm cloud that calls lightning on enemies), **Frost Cannon** (freezes enemies solid; frozen enemies take 2.5x damage and shatter) **Quake Cannon** (a shockwave that flings everything around you), **Sawblade Launcher** (a boomerang blade that cuts on the way out and back), **Levitator** (lifts enemies into the air, then drops them), **Mirage Projector** (a hologram of you that enemies shoot at), **Midas Rifle** (hit enemies turn to gold, and their kills pay out bonus points and drops), **Rewinder** (throws you back to where you were 5 seconds ago, with your old health), **Cluster Launcher** (a shell that bursts into 7 bomblets), **Prism Laser** (a continuous beam that does more damage the longer it stays on one enemy), **Seeker Launcher** (homing missiles), **Switcheroo** (swaps places with the enemy you hit) **Adrenaline Injector** (7 seconds of speed and damage resistance), **Phantom Cloak** (enemies cannot see you for 6 seconds), **Treasure Cannon** (fires a chest where you aim), **Plague Gun** (an infection that spreads from enemy to enemy), **Thruster Cannon** (hold fire to fly like a jetpack), **Squad Caller** (3 detailed allied soldiers in vests, helmets and visors who run, aim and fire for you) **Time Stopper** (freezes every enemy and bullet for 4.5 seconds), and twenty more: **Portal Gun**, **Necro Staff**, **Pinball Cannon**, **Napalm Mortar**, **Loot Vacuum**, **Mind Control Ray**, **Shrink Ray**, **Fortress Gun**, **Force Push**, **Hunter's Mark**, **Dash Cannon**, **Echo Pistol**, **Bullet-Time Rifle**, **Rage Totem**, **Reflector**, **Seer's Eye**, **Lunar Injector**, **Prism Splitter**, **Launch Pad Gun** and **Supply Beacon**, plus fifty more, each with its own trick: Hex Wand, Haste Syringe, Laser Fence, Caltrop Launcher, Sinkhole Gun, Slick Gun, Guardian Orbs, Longbow, Point-Blank Cannon, Headhunter, Gambler's Revolver, Combo Pistol, Overheat Rifle, Bowling Cannon, Link Gun, Sticky Bomb Gun, Venom Gun, Streak Rifle, Executioner, Overflow Gun, Missile Barrage, Meteor Wand, Smoke Launcher, Flashbang Gun, Banisher, Conversion Ray, Anchor Gun, Ghost Rifle, Smart Rifle, Taser, Confusion Ray, Drain Aura, Thorns Gun, Tesla Coil Gun, Skybridge, Overshield Projector, Terror Ray, Lure Gun, Chaos Gun, Avalanche Gun, Drill Gun, Doom Clock, Transformer, Jackpot Rifle, Revenge Gun, Golem Gun, Mortar Kit, Phase Gun, Glass Cannon, Metronome and the **Tank Caller** (calls in an allied tank for 30 seconds that chases enemies, shells them and crushes whatever it rolls over) and the **Deadeye** (a black steel sniper with a bone skull on the receiver, a fanged muzzle and glowing red veins; it kills anything in one shot, and a headshot reads 999,999,999 damage). The Deadeye and the Chaos Gun are the rarest things in the shop: each has its own 0.5% chance per restock. The Armory describes each one. **Spawner guns** (Sentry Kit, Hornet Hive, Squad Caller, Tank Caller, Golem Caller, Mortar Kit, Necro Staff, Rage Totem, Supply Beacon, Launch Pad Gun, Lure Launcher, Tesla Mine, Fortress Gun, Mirage Projector, Aegis Projector and Treasure Cannon) get their own spot: a separate SPAWNERS column next to the weapon list in a match, and a Spawners tab in the Armory. Each shop restock has a 10% chance to carry one. Chests have a 5% chance of being an **exclusive chest**: a huge magenta beam, an alert for every player ("EXCLUSIVE CHEST SPAWNED") and a random exclusive gun inside that you **keep for good** — it is added to your collection and you start every match with it (if you own them all already, the chest pays 750 points instead). The Chaos Gun and the Deadeye never come from chests; they are shop-only. Buy it once and you start every match with it, forever.

## Shop and points

You earn points by playing: 1 per Survival score point, 1 per 4 Free Play points, and 30 per Arena kill. Spend them in the **Shop** on profile pictures (41), gun skins (23), tracer colours (19), crosshair styles (13) and permanent perks (15 of them, from more starting wood, ammo and grenades, to Bloodlust (kills heal), Sharpshooter (+10% damage), Regeneration, Golden Touch (+50% points) and Second Wind (survive one killing blow per match)), in Common, Rare, Epic and Legendary rarities. Purchases and points are saved in your browser. The shop shows 11 items at a time and its stock changes every 20 minutes (on the clock, the same for everyone). Items you already own that have rotated out stay available under **Your items**.

Blast jumping: fire a Rocket Launcher or Grenade Launcher at the ground by your feet, or drop a grenade under you, and the explosion launches you high into the air (your own blasts do no damage).

## Controls

| Action | Keys |
| --- | --- |
| Move / jump / sprint | `W` `A` `S` `D` / `Space` / `Shift` |
| Shoot / reload / zoom | Click / `R` / right-click |
| Throw a grenade (knocks enemies back; you start with 3, ammo boxes give more) | `G` or the NADE button |
| Sniper scope | `C` |
| Switch gun | Mouse wheel or `Z` `X` |
| Open chest | `E` |
| Build mode | `Q`, then `1` wall, `2` floor, `3` ramp, click to place |

On phones and tablets the game shows touch controls automatically.

## Breno's Arcade as one file

`breno-arcade.html` is the whole arcade (all 39 games, about 9 MB) in a single file. Open it in Chrome: click a card to play, use the top-right "Arcade" button (or a game's own back link) to return. No server needed; a few games load web fonts or libraries and need internet for those.


## More chest guns

Twenty-four more guns can come out of chests: Peashooter, Trench Gun, Burst Pistol, Rivet Gun, Flare Gun and Carbine (common); Pump Shotgun, Lever Rifle, Scorcher, Ricochet Rifle, Magnum and Tactical SMG (rare); Battle Rifle, Storm Caster, Spear Thrower, Hailstorm LMG, Sniper Carbine and Slug Cannon (epic); Mega Rocket, Heavy Grenadier, Gauss Rifle, Doom Minigun, Titan AMR and Mine Layer Pro (legendary).

## Exotics on or off

An **EXOTICS: ON / OFF** button sits under the map picker. With it on (the default) you start every match with the exclusive guns you own; with it off you start with just the pistol and find guns from chests like everyone else. The choice is saved in your browser and applies to Survival, Free Play and online matches.

## Difficulty

The first waves are gentle and the fight builds from there. Wave 1 is three plain soldiers that are slower, weaker and slow to open fire; waves 2 and 3 send 5 and 7. Scouts only start showing up around wave 3 and heavies from wave 5. By wave 5 the soldiers are at full strength, and from wave 4 on the wave sizes are the same as before.

## More maps

Eight more maps, each with its own look and landmarks: **Red Rock Canyon** (sandstone arches and mesas), **Crystal Caverns** (glowing crystal clusters in a purple night), **Harvest Hollow** (autumn trees, hay bales and pumpkins), **Neon District** (glowing neon pylons between dark towers), **Xeno World** (alien egg pods and glowing spore stalks), **Hollow Graves** (gravestones, a mausoleum and iron fences in the fog), **Sunken Temple** (a stepped temple with a glowing-eyed idol and tall columns) and **Sugar Rush** (giant candy canes, lollipops and gumdrops).

## Play on GitHub Pages

A workflow (`.github/workflows/pages.yml`) publishes the game to GitHub Pages whenever `main` changes: the shooter is the site root (`index.html`) and the whole arcade is at `arcade.html`. Once Pages is on (Settings, Pages, Source: GitHub Actions), the address is `https://brenozlouzada-debug.github.io/priv/`.

Eight more after that: **Aurora Tundra** (ice spires under a green aurora sky), **Moon Base** (grey craters, domed habitats and a black starfield), **Mushroom Grove** (giant glowing mushrooms in a purple night), **Palm Beach** (golden sand, palm trees and beach umbrellas), **Dead Gulch** (a wild west ghost town of saloons and cacti), **Test Lab** (a clean white facility with glowing specimen tanks), **Coral Reef** (a sunlit seabed of coral fans) and **Iron Keep** (stone watchtowers with banners on green hills).

## A more realistic look and feel

The whole renderer was rebuilt around how light actually behaves.

**Colour.** Every colour in the game is written the way you would pick it in a paint program, as an sRGB hex. Light does not add or multiply correctly in that space, so the renderer now converts each colour into linear light on the way in and back out again at the very end, and tells the textures they hold sRGB pixels. three.js only started doing this for you in a much later version than the one here, so the game does it itself. Doing it wrong is the single thing that makes a renderer look flat and chalky; this is why the grass has depth now and the wood looks like wood.

**The sky.** The old sky was three colours blended together. The new one is shaped the way air behaves: the band near the horizon is bright because you are looking through far more atmosphere, the sun smears a warm halo forward into that band, the disc has a soft edge instead of a hard circle, and the ground bounces a little light back up from below. The same sky is prefiltered into an environment map, so it is also what lights the shadowed side of everything in the world.

**The sun sits lower.** A sun overhead flattens everything it touches. This one is partway down the sky, so shadows are long and shape reads properly.

**Post-processing.** The scene is rendered into a floating point buffer with the tone mapping off, so highlights keep their real brightness. The bright parts are blurred into a bloom, and one final shader does the film look in a single pass: exposure, the ACES curve, a grade, a touch of colour separation toward the corners the way a real lens has, a vignette, grain, and the conversion back to sRGB. The old CSS vignette and grain layers are gone — these land on the image itself rather than on a sheet above it. Phones keep the direct path, where the canvas gives them free antialiasing.

**Surfaces.** Ground, concrete, wood, metal, cloth and every weapon in the game carry a normal map derived from a height sketch drawn on a canvas, so a flat polygon catches light like a rough surface.


## Grass, trees and the horizon

**Grass grows in tufts.** It used to be single flat spikes scattered one to a square metre. Now one instance is a whole clump of curved, tapering blades, dark at the root and pale at the tip, and the clumps come in patches the way grass actually grows. Some of it is in seed and some of it dried off, and heights vary widely, because a real sward is never one colour or one length. The whole field bends in the wind: the blades lean by the square of their height, and the phase comes from each tuft's own position, so a gust crosses the field instead of every blade moving as one.

A blade of grass has no back — it is thin, it scatters light through, and the eye reads it by its own shape. three.js flips the normal on a back face, which was turning half the lawn black, so the grass and the leaves now keep one sky-leaning normal on both faces.

**Trees are branches, not stacked cones.** Each tree is built as a single mesh: a tapered trunk that leans, then whorls of drooping branches, each one carrying needle clusters that alternate off its spine with smaller twigs branching off those in turn. That second level is what fills a conifer in — a single row of needles reads as a bare stick. The crown is shaded off a normal leaning out of the middle of the tree rather than off each facet, so it reads as the rounded mass it is. The far forest uses the same model at a coarse level of detail in four shapes, so the ring does not look like one tree copied three hundred times, and it trades branch count for wider needles so the silhouette stays solid.

**The horizon.** A smooth cone reads as cut paper. The mountains now have their ridges pushed about with noise, and the rock is painted into the vertices with snow that follows height and flat ground instead of sitting on top as a separate white hat.

The gun and the camera behave more like a real one in your hands:

- **Recoil walks your aim.** Part of every shot's climb sticks to where you are actually pointing, so held fire drifts up and a little sideways. Stop firing and the muzzle settles back on its own; pull down to fight it yourself and there is nothing left to give back.
- **Breathing.** Standing still, your chest moves the sights in a slow figure of eight. A scope magnifies it.
- **Leaning and weight.** Strafing and hard turns tip the horizon, and walking rolls you side to side as well as up and down.
- **Rounds fly.** A bullet tracer is a short streak travelling at 420 m/s, not a line drawn instantly from end to end. Beam weapons still draw their whole line at once.
- **Shots echo.** Every loud gun slaps back off the treeline a moment after the report.
- **Bodies fall the right way.** A kill drops away from the shot that killed it, slides a little with its own momentum, and kicks up dust when it lands.

## Soldiers that look like soldiers

Everyone on the field — the hostiles, your squad and the player model your friends see online — is built the same way now: a waist narrower than the ribcage, a neck, rounded shoulders, tapered arms and legs, boots with a toe, and a helmet that is a real dome with a rim and a chin strap. The glowing red eyes are gone; soldiers wear dark goggles that catch the light instead, and a heavy wears a full face mask with a visor slit.

Both hands are placed on the weapon by a two-bone solver rather than by hand-picked angles, so the firing hand sits on the grip, the support hand sits on the handguard and the elbows fall where they have to. No two soldiers get quite the same faded uniform. Phones build a lighter version of the same model (45 parts instead of 70) so the frame rate holds.

The first-person gloves were rebuilt to match: a palm with a knuckle row, fingers that curl around the grip, a thumb over the top and a cuffed sleeve.

## Soldiers carry different weapons

A hostile is no longer always holding the same rifle. Each one is issued a weapon when it spawns, and it is modelled, aimed and fired differently:

| Weapon | Behaviour |
| --- | --- |
| **Rifle** | The standard: one aimed shot a volley, keeps a middle distance. |
| **SMG** | A four-round burst, sprayed wide, and it closes to about 8 m. Scouts favour it. |
| **Pistol** | Two quick shots, fired a little more often, at close to middle range. |
| **Sniper rifle** | One heavy, accurate shot every four seconds from about 26 m, with a thin fast tracer and a loud crack. |
| **Rocket launcher** | A slow smoking rocket that bursts over a 4 m radius — it will catch the soldier's own squad as well as you. Heavies only, and only from wave 6 does it become common. |

Who carries what depends on the type and the wave: waves 1 and 2 keep it to rifles (scouts get an SMG), scouts then favour SMGs and pistols, heavies start pulling out rockets, and grunts occasionally turn up with a sniper rifle. Each weapon changes how far away that soldier tries to stand, so a wave now spreads out instead of all crowding to the same ring. In co-op your friends see the same weapon in the same soldier's hands, and hear it.

## Dead soldiers drop their weapon

A kill leaves the weapon behind. It flies out of the hands, tumbles, and lands flat on the grass with a faint glow under it, and it stays there for about 25 seconds (blinking for the last five) before it is gone.

Walk over one to take it:

- a gun you do not carry yet joins your inventory with a part-filled reserve, and your current weapon stays in your hands — switch to it with the wheel or **X** when you want it
- a gun you already carry gives you ammo for it instead, and is left alone once that reserve is full

So a heavy with a rocket launcher is worth killing for more than the points, and a sniper rifle can be taken off the body of the soldier who was using it on you. The gun that drops is the one that soldier was actually carrying, and it keeps its own colours once the body has faded away.

## Your own explosives hurt you

A grenade, rocket, mine, cluster shell, sticky bomb or any other blast of yours now catches you if it goes off near your feet. The damage falls off with distance:

| Where it goes off | Damage |
| --- | --- |
| At your feet | about 55-65 |
| 2 m away | about 25 |
| 4 m away | about 10 |
| Past the blast radius | none |

The blast jump is still there, so a rocket at your feet will still launch you — it just costs you health now, which makes it a real decision rather than a free ride. Shots fired **at** you already did their damage through their own path, so nothing is counted twice, and a friend's explosion in co-op still cannot hurt you.

## Play with anyone, anywhere

The online screen has a **Play with anyone** card above the host and join cards. Press **Find a game** and:

1. It reads the public game list and joins the freshest open game with a free seat — any player, anywhere, no code to type.
2. If a seat is taken out from under you it moves on to the next game automatically.
3. If no game is open, you host one instead and your game goes on the list, so anyone pressing Find a game can drop into yours. Press **Start match** once someone is in.

The list is a shared public topic on the same ntfy.sh relay the number codes already use, so there is no account and no server of ours in the middle. A host announces `code, name, players, mode, map` every 11 seconds; a beacon older than two and a half minutes is dropped, a game showing 4/4 is skipped, and only the newest beacon for each game counts. The count refreshes the moment somebody joins or leaves, and the game keeps its place on the list after it starts so late players can still drop in.

Two things worth knowing: a public game is visible to **everyone** running the game, so use a number code instead when you only want friends; and matchmaking needs ntfy.sh to be reachable, so a network that blocks it blocks this too (**Test my connection** will say so).

## Your dog

**DOG: ON / OFF** sits next to the exotics toggle on the main menu. On by default; the choice is remembered in this browser, and flipping it mid-match brings the dog in or sends it home straight away.

With it on, every match starts with a dog at your heel, in survival, free play and online alike: a brown and white border collie.

The dog is a modelled mesh, not an assembly of spheres and boxes. Each part — body, head, ears, four legs, tail and the ruff — is one continuous surface swept along a spine from real cross sections, so it has a deep chest that reaches the elbow, a tucked loin, a sloping croup, an angled hock, a skull with a stop and a blunt muzzle. The section frame is carried from one ring to the next, which is what keeps a vertical leg from twisting and tearing.

The markings are painted into the vertices rather than stuck on as extra pieces: a dark mantle over the back, warm tan down the flanks, a white belly strip, white chest and collar, white socks, a white tail tip, and the blaze running up the muzzle between the eyes. The ruff, trousers and tail carry a ragged edge so the coat reads as fur.

**It is sculpted, not assembled.** The dog used to be separate parts — a body, a head, legs, a tail — each built by sweeping circles along a line and pushed into the next. That can never make a skull: from the side the head was a ball with a tube on it, from the front a teddy bear. Now the whole dog is one continuous surface sculpted offline, the way a sculpting program works: every part is a smooth shape set on a real anatomical landmark and blended into its neighbours. The ribcage is deep and narrow, with shoulder blades over it; the thigh carries real muscle and the hind leg angles back to the hock; the toes are separate. The head has a broad, flat skull, a distinct stop, soft brow ridges over eye sockets set either side of the stop on the front of the face — the eyes look forward over the top of the muzzle, the way a dog's do, rather than out of the sides of it — flat cheekbones, and a muzzle about as long as the skull that tapers in width and depth to a blunt nose, with the lower jaw tucked under the lip. The sculpt is meshed, reduced to eleven thousand triangles and shipped as 106 KB of compressed data; the script that makes it is in `tools/dog/sculpt.py`.

A skeleton is fitted to it when the game loads, with the same joints the movement code already drives, and every vertex is weighted to the bones nearest it, so a run, a sit and the crouch bend one skin rather than moving separate pieces. The legs are solved rather than swung: the body is placed first, and then each leg works out its hip and knee angles to put its paw on its spot on the ground. That is what makes the feet plant and stay planted on the trot, the haunches fold properly on the sit, and the crouch drop the body down onto bent legs.

**The ears** are leather now, not paddles: a broad triangle cupped so the inside faces forward, standing on its base with the top third tipped over — the semi-erect ear the standard describes. They are pink-brown and nearly bare inside, brown and furred behind, with a fringe of longer hair round the edge.

**A working dog's body, not a sighthound's.** The first sculpt had a greyhound's waist: the belly line shot up behind the ribs and from above the body was a narrow tube. A collie has well-sprung ribs that reach well back, a short strong loin and a moderate tuck-up, so the ribcage is broader and longer, the loin is fuller, and the underline rises gently instead of in a step.

**Hair that looks like hair.** Each hair is a tapered strand, thick where it leaves the skin and a fine point at the tip, and as the fourteen shells climb, each hair is cut thinner until it ends at its own length. The hairs are scattered rather than set on a grid, and their lengths follow a coarse pattern of clumps, so the coat breaks into locks instead of reading as a carpet of identical dots. Each hair leaves the skin along its normal and then bends over to lie the way the coat runs, and the long ones sag under their own weight. Light comes through the tips at a glancing angle, the way it does through a real coat. The texture's shrunken copies, used as the dog gets further away, are built to keep the strands rather than averaging them into the gaps between them; with ordinary ones, the long feathering simply vanished a few metres off. The coat is longer where a rough collie carries it: the mane, the feathering down the back of the forelegs, the britches, the belly fringe and the tail plume.

The coat grows on the sculpt the same way as before, but now as one skinned layer per shell that bends with the skeleton. With no UV map to lean on, each hair is looked up from where the skin sits at rest, along whichever axis it faces, so the hairs stay the same density everywhere and hold together however the body moves. If a browser cannot decompress the sculpt, or a match starts before it has finished loading, the old hand-built dog stands in and is swapped for the real one the moment it is ready.

**It is a brown-and-white border collie, checked against the breed standards.** The UK Kennel Club, FCI and AKC standards agree on the numbers, so the model is measured against them by a script rather than judged by eye: body a little longer than the dog is tall (10:9), the bottom of the chest level with the elbow, a head about two-fifths of the height at the withers with skull and muzzle roughly the same length, and a tail that reaches the hock. The measuring turned up three real faults — the body was a quarter too long, the head a quarter too big, and the tail tip went seven centimetres into the ground.

The colour follows how brown collies actually look. The coat is one solid chocolate, not a tan dog with a black saddle. The white is in the classic Irish pattern: a narrow blaze between the eyes opening onto a white muzzle, a full collar running down into the chest, stockings on the forelegs, white hind feet and a white tail tip. The nose is black, by request; the eye rims and pads stay brown, and the eyes are amber rather than dark brown. The white is a warm off-white, never paper white.

The coat is rough, like most working collies: short and smooth on the face and down the front of the legs, long in the mane round the neck, feathered down the back of the forelegs, full britches on the thighs, a fringe under the belly, and a plume under the tail. Each part of the coat gets its own hair length from its position and the way its surface faces, so one leg can be feathered behind and short in front. Every hair also has its own shade, because a coat where all the hairs match looks like felt however well it is shaped.

**It is built like a working collie.** Lean through the barrel — narrow side to side, deep from the withers down to the elbow, with a real tuck-up at the loin instead of the barrel it used to be. The foreface is about as long as the skull and deep through, so it reads as a wedge in profile: longer and finer than that and the dog turns into a fox, shorter and it is a terrier. The tail is set on low and reaches past the hock, carried down in a long curve with the tip swinging back up — the swirl a collie shows at rest — and it is heavily furnished, so it moves as a plume rather than a stick.

**The markings are measured against the dog, not in centimetres.** A blaze that looks right on the forehead swallows the whole muzzle if you give it a fixed width, because the muzzle is narrower. Every marking is now a fraction of how wide the body is at that point: the saddle draping over the back and down the ribs, a white collar all the way round, the chest bib, the socks, the tail tip, and the blaze running up between the eyes. Each edge is crisp but wobbles, the way a real marking does, rather than fading out over a centimetre.

**Dark fur is glossy and white fur is matt.** That is what gives a dark-coated dog the hard sheen along its back. three.js has no per-vertex roughness, so the shader reads it off how dark the vertex colour is, which is exactly the signal we want: the saddle picks up a sheen, the ruff and socks stay soft.

**It is furry.** A coat modelled as one smooth surface reads as painted plastic however good the markings are, because what the eye looks for is the broken edge. The fur is built in shells: the coat mesh is drawn four times over, each copy pushed a little further out along its own normals, and a noise texture holding one hair per cell decides which hairs are long enough to survive each layer. Looking through four of them you see strands, with the darker skin showing between them at the roots. Each layer also slides a little the way the coat lies, which combs it — straight-out shells look like moss. The body, the ruff, the trousers, the tail, the head and the ears each have their own hair length and direction. Phones skip it.

Fixing this turned up an older bug: the hull builder that makes the dog was winding its triangles inside out, so every normal pointed into the body. It had been rendering by accident, because a two-sided material flips the normal on a back face and that happened to undo it. The winding is right now, which is also why the coat is lit properly for the first time.

**Its ears are collie ears**: a broad triangular blade carried upright with the top third tipped forward, dark and furry on the back, bare and warm-toned inside.

It has proper eyes. Each one is a brown eyeball set into the skull at the stop, just proud of the surface the way a real eye sits, with a dark pupil on the front, a white catchlight, and a dark almond lid rim around it slanted so the eye is not a circle. The nose has two nostrils in the same way. It costs 27 meshes and 4,900 triangles, and phones build a lighter version (23 meshes, 2,600 triangles).

## How the dog moves

A border collie does not amble. It works in bursts, and the dog now has a state for each of them:

- **Trot** — the working gait, off your left shoulder and out of your line. Legs move in diagonal pairs.
- **Run** — flat out when you get more than four metres ahead, up to about eight metres a second. The back legs slide toward the front pair as it opens up, which turns the trot into a gallop.
- **Dart** — when whatever it is following cuts hard across it, it throws a turn at up to thirteen radians a second and banks into the corner. Half a second, then back to work.
- **Creep** — a soldier out at nine metres: it stalks in low, working round the side rather than straight at it.
- **Eye** — the thing collies are famous for. Body down, head level with the shoulders, stare locked, dead still. It holds it for about two seconds and then breaks, because a dog that crouches all match is a statue. Stand still yourself for a moment and it will give *you* the eye too, then shake it off and not do it again for a few seconds.
- **Idle and sit** — weight shifts, ears tracking, then down on its haunches.

Underneath, it accelerates at seventeen metres per second squared and stops nearly as hard, because that snap is most of what reads as a dog rather than a vehicle. Turning has real angular momentum rather than snapping to a heading, and the body banks, the legs lean and the head and tail roll with it. The centre of gravity drops as it speeds up and drops further on the crouch. Its ears prick forward at whatever it is watching.

It walks around crates and walls the way you do, follows the ground up and down slopes, and catches up out of sight if a fall or a teleport leaves it far behind. Its tail wags faster the closer it is to you, streams out flat on the run and goes still on the eye. It barks now and then on its own, and sharply when a soldier comes within nine metres.

**It cannot be killed.** It is not a target: nothing shoots at it, explosions do not touch it, and there is no health on it to lose. It does not fight either — it is company, not a weapon.

The dog is yours alone: in an online match each player sees their own, not each other's.

## Explosions leave fire behind

Every blast now sets the ground alight: a scorched patch with flames licking over it, smoke drifting up, and a glow that lights the ground around it at night. The fire lasts five to nine seconds depending on how big the blast was, then dies down and goes out.

**Standing in it hurts.** You take damage every third of a second while any part of you is in the flames, so walking through costs a little and standing in it costs a lot — step out and it stops. Soldiers burn in it too: they take damage and catch fire for a couple of seconds after they leave. Your dog is the one thing it cannot touch.

A blast high in the air lights nothing, since there is no ground under it to burn. Fires are capped (14 at a time, 7 on phones) so a heavy firefight cannot bury the frame rate, and they share a single light rather than one each.

**How the fire looks.** The flames used to be rigid orange cones. Now each fire is a cluster of soft tongues drawn by a shader: scrolling noise bends, splits and narrows each one, so the flames lick upward, sway, flare and flicker instead of standing still. Their colour follows how fire actually glows, from deep red at the edges and tips through orange to a pale yellow core, and the core is bright enough for the bloom to catch. The flames also partly hide what is behind them, so they read as fire in daylight instead of a faint orange tint. Under them the ground is blackened and crazed with thin cracks of glowing embers that pulse. Sparks rise off the fire and drift and twinkle as they climb. The smoke is dark and sooty and spreads as it rises. The firelight flickers on several rhythms at once, so it never settles into a steady beat. When the fire dies the flames shrink and the bed cools before it goes out.

Burning soldiers now have real flames clinging to them instead of orange puffs, with a trail of smoke.

All of the flame, spark and ember-bed movement runs on the graphics card, so a fire costs three draw calls and almost no per-frame work.

Fixed along the way: the **Laser Fence** did no damage, because a helper with the same name, added for the dog's skeleton, replaced the one the fence used. Each now has its own name, and the fence burns again.

## Explosions

Explosions were a white sprite, a flat orange ball and a hard ring on the ground. Now a blast plays out the way a real one does on film, over about three seconds:

- **The flash.** A white-hot burst lasts a split second and lights everything around it. The light flares hard, shifts from white-yellow to orange, and dies away with a flicker.
- **The fireball.** It isn't one ball but a cluster of lobes that boil out from the centre. The upper lobes rise faster, so the cloud climbs and rolls. They're shaded with churning 3D noise: hot yellow inside, orange-red at the edges.
- **Fire into smoke.** Each lobe cools from the outside in. The fire breaks up into glowing pockets and then into heavy, sooty smoke with ragged billowing edges. The smoke is lit orange from underneath while the fire lasts, then rises and thins away. It takes its colour from the sky above it: grey by day, dim blue-black under moonlight.
- **Sparks** streak outward and arc down under gravity, hottest at their heads.
- **The shockwave.** A faint bright shell races out in the first instant. On the ground, a ragged ring of dust is thrown outward and settles.
- **Aftermath:** debris flies, a scorch mark is left on the ground at its real height, and the ground keeps burning.

The fireball, sparks, shockwave and dust are all shaders, so a blast is only a few draw calls. When several go off at once, as with a cluster bomb or a missile barrage, each one is built with fewer lobes so the frame rate holds. Phones also get fewer lobes and sparks.

## A much bigger field, with a coast

The playing field is now 220 m across instead of 80, nearly eight times the area. It's filled to match: about four times the crates, containers, barrels, trees and scenery on a computer (two and a half times on a phone), and far more grass and flowers. The distant mountains and forest ring have moved out with it. Hostiles now arrive 28 to 46 m from wherever you are, so a fight never starts on the far side of the map. There are twelve chests instead of six, more medkits and ammo boxes, and online spawn points are spread across the bigger field. Shadows now follow you in a box around where you stand, so they stay sharp however far you roam.

## The sea

Every map except the Moon has a coast along its north side: grass gives way to a sand beach, then shallows, then a seabed that drops away to deep water. Beyond the line of red buoys the sea runs out to the horizon. The water is drawn by a shader rather than a texture:

- **Colour follows depth.** It's clear green-blue over the sand and darkens to deep blue further out. You can see swimmers' legs and the seabed through the shallows; deep water is opaque.
- **The surface moves.** Travelling waves make a swell that flattens in the shallows, with fine ripples close up.
- **It reflects the real sky** of each map and catches the sun in a glittering path.
- **Surf breaks** in a moving white line along the beach.

Each map tints its own water: dark and still at night, green under Ashfall's ash, pink on Sugar Rush, turquoise at Palm Beach and the Coral Reef.

**Swimming.** Walk into water and you wade, slowed. Once it's too deep to stand you swim, with your head just above the surface, bobbing on the swell, at about half speed, with stroke sounds and splashes. You can't jump in water, and you climb out by swimming back to the beach. Soldiers swim too: they tread water with their head and shoulders up, kicking under the surface, with a ring of ripples around them. When you're near the coast, about a third of each wave comes out of the sea and has to swim ashore under your fire. Your dog paddles along with its head out.

Bullets that hit the sea throw up a splash. An explosion on the water raises a column of spray instead of a scorch mark, and nothing burns on water.

## Warships

In survival, two destroyers patrol the bay (one on a phone):

- **The ship itself** has a lofted hull with a raked bow, a black stripe along the waterline, a pennant number on the bow, a bridge with windows, a funnel trailing smoke, a tripod mast with a sweeping radar, lifeboats, railings and an ensign. A foaming wake spreads behind it.
- **It shoots at you.** Each ship carries two twin-gun turrets that train round onto you and lob shells at you from up to 120 m, leading you a little. Each shot comes with a muzzle flash, a cloud of smoke and a boom. The shells come down in an arc and explode.
- **It sends soldiers ashore.** Every so often a few soldiers jump over the side and swim for the beach.
- **You can sink it.** It takes a lot of damage from bullets and much more from rockets and grenades, starts burning at half health, and when it goes, a chain of explosions runs down the hull before it settles by the stern and slips under. Sinking one is worth 150 points. Another steams in from the horizon about 45 seconds later.

Ships show up on the minimap and you can't swim through them.

## Bosses

Every fifth wave is a boss wave: a boss leads it in with half the usual escort, a horn sounds, and the boss's name and health bar appear across the top of the screen.

- **The Juggernaut** (waves 5, 15, 25…) is twice a man's height in black armour, with a glowing red visor. It carries a minigun whose barrels spin as it fires. Every few seconds it looses a four-rocket salvo from the pods on its shoulders, and if you get close it stamps the ground, a shockwave that hurts and throws you back.
- **The Warlord** (waves 10, 20…) wears a crested helmet, gold-trimmed pauldrons and a long red cape, and fires a three-round battle rifle. It leaps across the field, landing in a shockwave next to you, and keeps calling in squads of three soldiers.

From wave 15 on, both come together. Bosses get tougher with every wave. Killing one is worth 200 points, sets off a huge blast, and leaves a **legendary chest**, a medkit and ammo where it fell. The Juggernaut also drops its minigun for you to pick up.

## Soldiers, rebuilt again

The soldiers have a new look:

- **Uniforms are printed camouflage**, woodland for riflemen, desert for scouts and dark urban for heavies, each with its own randomly drawn pattern.
- **The body** is one rounded, turned shape (hips, waist, ribcage, shoulders) instead of stacked cylinders.
- **The kit:** a moulded plate carrier with MOLLE webbing, three magazine pouches with flaps, an admin pouch and a radio with a whip antenna. On the back is a pack with a bedroll, and a drinking tube runs over the shoulder.
- **Every soldier has a face:** eyes, brows, a nose, a mouth, ears and a stubbled jaw.
- **Headgear by type.** Riflemen wear a covered ballistic helmet with a night-vision mount, side rails and goggles pushed up. Scouts wear a boonie hat and shades. Heavies wear a full ballistic face mask.
- **Red marks a hostile.** A red band round the helmet or hat, and a red armband, mark every enemy at a glance.
- **Limbs and boots** have cargo pockets, knee pads, rolled cuffs, gloves with fingers, and boots with real soles.

This also fixed an old colour bug. The tint that gives each soldier a slightly different uniform was lightening every colour by one gamma step, which is why the old uniforms looked pastel pink and yellow. Online players' models get the new build in their team colours.

## Less lag

The bigger field had made each frame far heavier, so the game was rebuilt to draw less:

- **Static things are merged.** Every separate mesh is a separate draw call. A map's props now become one mesh per material, so a few hundred crates, barrels and rocks cost a handful of draws. The boundary walls and each chest are merged the same way, and so are a ship's fittings.
- **Soldiers are merged too.** A soldier was 89 draw calls; now it's 16. For a hostile, the head and arms never move against the torso, so the whole upper body is one piece. Every plain-coloured part shares one vertex-coloured material, with one more each for the camouflage and the webbing. Online players' models keep a moving head and arms.
- **Grass is in chunks.** It's split into a 9 × 9 grid, and only chunks near you and in front of you are drawn: within 85 m on a computer, 55 m on a phone. That alone cut more than a million triangles from a frame on the grassier maps.
- **Phones get less scenery:** about twice the old prop count instead of two and a half times, and less grass.
- **Resolution follows the frame rate.** If frames start taking too long, the game renders at a lower resolution (down to half) until they recover, then climbs back to full sharpness.
- **Fixed in passing:** the far forest ring and flowers could vanish when the middle of the map was behind you, because three.js culls an instanced mesh by the bounds of a single copy.

Together this took a typical frame from about 2,700 draw calls to under 800 on a computer, and from about 1,300 to about 560 on a phone.

## Allies, rebuilt

Your Squad Caller soldiers and the undead the Necro Staff raises now use the same build as everyone else on the field:

- **The squad** wear blue-grey digital camouflage, with blue bands on the helmet and arm instead of the hostiles' red, so you can tell them apart at a glance. Their heads and arms still turn to aim.
- **The undead** wear a rotting shirt torn open over their ribs. They have green skin, glowing green eyes and messy hair, and reach forward with bare hands.
- **Both swim.** Allies tread water instead of walking along the seabed.

## A field worth fighting over

The open field has been given real cover and landmarks:

- **Sandbagged positions:** U-shaped and open at the back, laid in staggered rows of burlap bags. Bullets that hit them kick up dirt.
- **Broken brick walls:** L-shaped, with ragged tops, a window gap and rubble at the foot.
- **Concrete pillboxes** with a firing slit, a door at the back and sandbags on the roof. You can stand on top.
- **Wooden watchtowers** on four braced legs, with a railed platform and a roof.
- **The beach** has steel anti-tank hedgehogs along it, and a wooden pier on piles runs out into deep water, with bollards and a lamp at the end. You can walk out along it, or swim underneath.
- **Worn dirt tracks** wind across the field, with darker wheel ruts and ragged edges, and grass doesn't grow on them. Each map has its own track colour: snowy slush, desert sand, red canyon dust, ash. There are none on asphalt or the Moon.

The fantasy maps (Sugar Rush, Mushroom Grove, Crystal Caverns and Xeno World) skip the fortifications. Everything new is merged into a few draw calls with the rest of the map, and bullets and players are stopped by plain hidden boxes.

## Your gun and hands

- **Your gloves:** charcoal tactical gloves with a padded knuckle guard, two-jointed fingers wrapped round the grip, a thumb over the top and a velcro cuff. Your sleeves are woodland camouflage and run off the bottom of the screen.
- **The pistol** is built from side profiles with rounded, bevelled edges instead of boxes. It has a slide with a chamfered nose, front and rear cocking serrations, an ejection port and a dot front sight. Below that are a frame with an accessory rail and a real trigger-guard opening, and a swept grip with a beavertail and stippled panels.
- **The assault rifle** gets the same treatment:
  - profiled upper and lower receivers with the magwell and trigger guard
  - a full-length rail with teeth
  - a slotted handguard and a muzzle brake
  - a shaped stock on its buffer tube with a butt pad
  - a curved magazine and a tube red-dot sight

## Snow and night

Frostbite's snow was clipping to flat white. It is now a touch greyer and lit a little less, so drifts and footprints of light and shade show. Moonlight is a little brighter, so the field reads at night without losing the dark.

## Lighter frames, again

- **The distant forest** uses a coarser tree and fewer of them.
- **The ground mesh** is coarser (the beach and hills don't need more).
- **Grass** is drawn out to 70 m on a computer and 45 m on a phone.
- **Shadows** are redrawn every other frame (every third on a phone).
- **The first-person gun's** fixed parts are merged.

All soldiers now share one camouflage mask texture, with each pattern's colours mixed in the shader. A colour bug was found and fixed: the slight brightness variation between uniforms could go over white and turn some soldiers black, blue or yellow.

## Building it

The build scripts and browser tests live in `tools/build`:
- `mkstandalone.py` makes the offline single file.
- `mkarcade.py` updates the arcade bundle and stages the published pages.
- `mkdbg.sh` makes a debug build for testing.
- `harness.js`, `t_smoke.js` and `t_play.js` run the game headless in Chromium.

## No more stutter on every shot

Rockets, explosions, storm clouds and vortexes each used to bring their own light into the scene. three.js builds every lit material's shader for an exact number of lights, so each of those made every material in view recompile: a visible hitch on every rocket and every blast.

Now the scene holds a fixed set of six point lights (four on a phone) from start to finish. An effect gets a stand-in carrying its colour, brightness and position. Every frame, the real lights take on the brightest stand-ins nearest you, and a stand-in is let go as soon as its effect leaves the scene. The fire light also exists from the start, so the first fire no longer causes a hitch.

The effects' shaders (flames, embers, the burning ground, fireball lobes, sparks, the dust ring, the shockwave, ship wakes, swimmers' ripples and the soldier and boss materials) are all compiled once at the start of your first match, with the same settings the scene is really drawn with. A test that sets off three blasts, a rocket and a fire now compiles no new shaders at all. Before, it compiled seven, and the old light churn had left 65 programs where 42 do the job.

Also:
- Shadows use plain PCF filtering instead of the soft variant, which samples far more per pixel for a small difference.
- In a heavy fight, smoke puffs are capped (180, or 90 on a phone), and the oldest smoke goes first.
- Phones use a coarser ground mesh.

## Soldiers with real bodies

Every soldier on the field (hostiles, bosses, your squad, the undead and your friends' models online) now has a sculpted body instead of a stack of cylinders and spheres. It is one smooth surface, modelled offline in `tools/soldier/sculpt.py` and shipped compressed (64 KB, 7,000 triangles):

- **Boots and legs:** flat-soled boots with trousers bloused over them, a calf and shin, a real knee, and a thigh with the quad muscle.
- **The torso:** glutes and a belted waist, a ribcage with the pecs and lats, trapezius and deltoids.
- **Arms:** a bicep and forearm, and a gloved hand with a thumb.
- **The neck:** with the shirt collar round it.
- **The face:** a skull with a jaw, chin and cheekbones, a brow ridge over eye sockets, a nose with nostril wings, lips and ears.

The body is skinned to the ten joints the rig already animates (hips, knees, shoulders, elbows, torso and head). So it bends smoothly when soldiers walk, aim, swim, lean and fall, and their arms wrap round whatever gun they're carrying. One material colours it:
- **The camouflage** is projected onto the body in its rest pose, so the pattern stays put on the cloth as the limbs move.
- **Skin, gloves and boots** are coloured by region.
- **The undead** get green bare hands.

All the kit stays as it was: helmets, hats, plate carriers, pouches, packs, knee pads, masks and the bosses' armour. Each soldier now draws in fewer pieces than before.

## Warships, rebuilt as modern destroyers

The destroyers were redrawn with a modern warship's lines:

- **The hull** has weathered plating with welded seams, rust weeping from the scuppers and grime along the waterline. A white bow wave curls off the stem as it moves.
- **The deck** is dark non-skid with a painted walkway, and there's a helicopter pad on the stern with its circle and H.
- **The superstructure** is built from sloped, stealthy blocks. The bridge has a raked window band, wings and red and green running lights. Flat octagonal radar arrays look out from the bridge and the hangar.
- **Above it** are twin raked funnels with black caps, and a slim tapered mast with yardarms, antennas, a satellite dome and the sweeping radar.
- **Weapons:** a faceted main gun forward and a second mount aft, each with one long barrel. There are banks of missile hatches set into the deck fore and aft, and close-in weapon domes.
- **Fittings:** rigid-hull boats in davits and life-raft canisters along the rails.

## A much lighter frame for the processor

A profile of a busy wave-10 fight found that most of the game's own per-frame time was spent walking the scene graph, not running the game:

- **Every first-person gun model was attached to the camera.** That is over a hundred guns and thousands of hidden parts, even though only the one in your hands is shown. Now only that one is attached.
- **Merged-away originals stayed in the scene.** When static parts were merged into one mesh, the originals were only hidden, so three.js still walked thousands of them every frame. They now leave the scene graph; props that stop bullets keep their last position for aiming rays.
- **The map's transforms are frozen.** Nothing in a map moves once it is built, so its transforms are no longer recomputed every frame.

The game's own update in that fight went from about 8.8 ms a frame to about 3.5 ms. The renderer saves about as much again, because it walks the same scene.

## A more natural look

- **The field ends in nature, not concrete.** On the outdoor maps the concrete boundary walls are gone: they still stop you, but you can't see them. The field ends in a dense belt of trees right along the edge, or rock spires on the dry maps, the way a real clearing ends. City, Neon District, Test Lab, Iron Keep, Dead Gulch and Moon Base keep their walls, because walls belong there.
- **A calmer colour grade.** The final pass used to push saturation up and add contrast. Now it pulls saturation down a little and keeps contrast gentle, so greens, skies and sand look like the real thing rather than paint.
- **Grass and ground with real variety.** Grass is less saturated, and more of it is dry, gone to seed or in shade. The ground's own colours (soil, sand, snow, ash) are toned down toward their natural greys.

## Three new maps: Pirate Cove, Robot Foundry, Cartel Jungle

Each new map has its own enemies, their own guns and its own ship. One ship sails, one drives on land and one flies.

- **Pirate Cove: pirates and a galleon.** A tropical cove with palms and wrecks. Pirates wear sashes, bandoliers and gold earrings, with tricorn hats or bandanas, and most have full beards and moustaches; the captains wear long coats. They fire **blunderbusses** (a wide spray of shot), scouts carry pistols, and the captains, **Captain Ironhook** and **Captain Blackheart**, carry brass **swivel guns**. A three-masted **pirate galleon** sails the bay under full canvas, flying the skull and crossbones, and fires broadsides of cannonballs from whichever side faces you. Sink it and another sails in.
- **Robot Foundry: robots and a tank.** A dark, red-skied industrial yard with silos, containers and tanks, and no sea. The robots have smooth helmet heads with a chrome face plate, a vent grille, a dark visor band and glowing eyes, plus painted armour panels with seams and rivets, rubber joints, a glowing chest core and an antenna. They fire **laser blasters** (red bolts in threes); heavies carry a **laser cannon**, and the bosses are the **Titan Unit** and the **Command Unit**. A **tank drives across the field on its tracks**, following the ground, kicking up dust and smoke. It turns its turret to fire shells at you, lets robots out of its back hatch, and shoves you aside if you get in its way. Knocked out, it burns and the wreck sinks away.
- **Cartel Jungle: mercenaries and an attack helicopter.** Dense jungle with ruins. Cartel gunmen in tiger-stripe camo carry regular guns; the bosses are **El Jefe** and **The Enforcer**. An **attack helicopter flies** low circles over the field, nose-down and banking into its turns. It ripples rockets off its stub wings, rakes you with its chin gun and hovers to drop gunmen down ropes. Shot down, it spins out of the sky and explodes.
- **Made in Blender.** The robot body is built in Blender from the same base mesh as everyone else (`tools/creatures/make_creature.py`), with its head shaped into a squared-off helmet. The galleon (planked hull, gun ports, three masts with bellied sails), the tank (tracks, road wheels, a separate turret and gun), the helicopter (separate main and tail rotors), the laser blaster, the blunderbuss and the tricorn are all modelled in Blender (`tools/props/make_props2.py`).

## Aliens, sea monsters, saucers and submarines

Each map now has its own enemies and its own ship.

- **Moon Base and Xeno World: aliens.** Tall, slim aliens with a swollen cranium, big glossy black almond eyes, a pointed chin and a slit of a mouth, grey-green mottled skin, long fingers. They wear sleek dark suits with glowing seams (a chevron on the chest, the spine, the cuffs and a stripe down each leg), a glowing emblem and buckle, and a chrome power pack on the back; the big ones have chrome pauldrons. The bosses become **The Overlord** and **The Xeno Warlord**.
- **Coral Reef: sea monsters.** Fish-men with a long, flat head, bulging gold eyes, a wide mouth full of small sharp teeth, gills on the neck, a crest down the crown, fan fins for ears, a fin down the back and along the forearms and calves, and webbed flippers for feet. The skin is scaled: dark down the back, pale on the belly, blotched. The big ones wear barnacled shell armour. The bosses become **The Leviathan** and **The Tide King**.
- **Guns you can't get.** Aliens fire **ray guns** (chrome with glowing coils, two-shot green energy bolts), heavies carry a **plasma cannon** that lobs glowing balls that burst, and the Overlord has a **ray repeater**. Sea monsters fire a **harpoon gun** (crusted bronze with a bone stock and a coil of line) that shoots real harpoons; the big ones fire **harpoon volleys**. None of these are ever dropped when they die.
- **The alien saucer** (Moon Base, Xeno World). It hovers high over the field in a slow wobbling orbit, its rim turning with chasing lights, portholes lit, the drive glowing underneath. It fires plasma balls from three pods, and every so often switches on a tractor beam and sets aliens down on the ground. Shot down, it trails fire and smoke, tumbles out of the sky and blows up where it lands. Another comes down from the sky later.
- **The submarine** (Coral Reef). It surfaces as it arrives, blowing its tanks, and runs with its deck awash. It launches missiles from the tubes behind the sail that climb in a column of smoke and come down on you, and sends sea monsters over the side to swim in. Every other map with water keeps the warships.
- **Made in Blender.** The two creature bodies are built from the same Blender Studio base mesh as the soldiers (`tools/creatures/make_creature.py`), so they share the soldiers' skeleton, skin weights and animations; the heads are resculpted, the human face smoothed away, and the fins, crest and eyes modelled in Blender. The ray gun, harpoon gun, harpoon, saucer and submarine are modelled in Blender too (`tools/props/make_props.py`) and shipped with their own colours and glow.

## Warships that look like real destroyers

- **A destroyer's hull.** The hull is longer and much slimmer: 34 long by 4.3 wide, the slender 8 : 1 of a real destroyer, where it used to be a stubby 5.5 : 1. It's lofted from more stations, with a fine entry, a forecastle that flares and rises toward the raked stem, and a knuckle down the sides.
- **Haze-grey paint, not shiny metal.** Flat, slightly chalky naval grey. The plating has faint welded seams, a few touched-up plates, scuppers along the deck edge with thin weathering streaks, and only a little grime at the waterline, not rust everywhere. The superstructure has its own subtle panel seams.
- **One stealthy superstructure.** A long deckhouse with sloped sides and the bridge stepped up at its forward end, with raked windows and bridge wings. Framed phased-array radar faces sit on the bridge front and the deckhouse's after wall. Amidships is a low angular stack with two exhaust outlets, and aft a hangar with a roller door opening onto the flight deck.
- **A real mast.** The cone mast is replaced by a tapering four-legged lattice with platforms, yardarms and antennas, the turning air-search radar on top and a radome on a bracket.
- **Properly scaled kit.** A faceted main gun with one long, slim barrel on the foredeck and a lighter mount on the hangar roof. Vertical launch cells sit flush in the deck fore and aft, and close-in weapons stand on pedestals. Rigid inflatable boats sit in recesses by the stack in place of the big orange lifeboats, along with life-raft canisters, hawse pipes and anchors, a jack staff and a smaller ensign.

## Soldiers built from a real human model

- **A real body, made in Blender.** Every soldier, ally and online player is now built on Blender Studio's realistic male base mesh, from their free Human Base Meshes bundle (CC0, sculpted by Dan Ulrich), in place of the hand-built shapes. It has real anatomy: a properly sculpted face with eyelids, a real nose, lips and ears, and real proportions for the neck, shoulders, arms, hands and legs.
- **Fitted to the game's skeleton.** In Blender the model gets bones at its own joints and bone-heat skin weights. Its A-pose is then straightened onto the game's rig: arms hanging, legs straight, the head set back over the spine. The rig's shoulders and hips moved to where a real body has them, and the arms' reach was updated so hands still land on the rifle grip.
- **Dressed as a soldier.** The uniform is the body smoothed over (no muscles or anatomy show through) and let out a little. The trousers are bloused into real combat boots (a shaft, a toe cap and heel, a flat sole), the hands are snug gloves, and there's a collar at the neck.
- **Game-sized.** Blender reduces the body to about 12,700 triangles, about what the old one used, keeping the face much denser than the clothes. It ships with its eyeballs, its skin weights and a region per vertex (uniform, skin, glove, boot, eye).
- **Painted to match.** Brows taper from a fuller inner end and are drawn as short hairs. The eyes sit a touch deeper under the lids, with a shadow from the upper lid. Lips, stubble, warmth on the nose, cheeks and ears, and the lash line are all placed on the new face. Skin tones are a little warmer, so the palest no longer washes out.
- **Relaxed eyes.** The base mesh's eyes are wide open, so the upper lid is painted down over the top of the iris and the lower lid up to its bottom edge, with the lash line along the lid. There's no ring of white round the iris any more.
- **Undead hair that fits.** The undead's hair is painted onto the scalp itself: a ragged crop that follows the skull down to a hairline over the brow, above the ears and at the nape, with a few bare patches and a matte finish. It replaces the cap that sat on top of the head.
- **Gear refitted.** The boonie hat, the scout's sunglasses and the heavy's face mask were moved to fit the new head.

The pipeline is in `tools/soldier`: `fit_human.py`, `clothe.py` and `reduce.py`, run with Blender's Python module (`pip install bpy`).

## Real faces, and leaner soldiers

- **A sculpted head.** The head is now sculpted on its own at a much finer level of detail than the body: a skull with a forehead, brow ridge, cheekbones and temples, a defined jawline and chin, a nose with a bridge, tip, wings and nostrils, upper and lower lips with a groove above them, and ears with a rim and a hollow.
- **Eyes that look back.** Each eye is a real eyeball set between upper and lower lids, with a white, a coloured iris with a darker rim, and a pupil, angled slightly inward so the soldier seems to focus on you.
- **Painted skin.** The face is coloured in the shader: warmth on the nose, cheeks and ears, the lips, a day's stubble, eyebrows and a lash line in the soldier's hair colour, and a little shade in the eye sockets. The old stuck-on eye and brow pieces are gone.
- **Every soldier looks different.** Each enemy gets one of eight skin tones and its own hair and eye colour. Undead keep their green skin and glowing eyes; heavies and bosses keep their masks.
- **Less chubby.** The faces are narrower, with slimmer cheeks, a firmer jaw and no jowls. The neck is slimmer too, and the body is trimmed at the belly, hips, thighs and arms. Shoulders stay broad, so the soldiers read as fit, not thin.
- **Sunglasses that fit.** The scout's wraparound shades now have arms that run back to the ears.

## Why online play said there was no internet

On the published site, hosting a game used to burn through the public code relay's allowance in about a minute: the host posted three seat offers, then polled three separate topics every two seconds, roughly ninety requests a minute from one address. ntfy.sh rate limits anonymous traffic, so it started answering 429 and every call after that failed with "check your internet". On the claude.ai copy this never showed, because that copy signals through its own database first and only falls back to the relay.

The relay protocol now uses two shared topics for a whole room instead of six, polls once per cycle, and slows down while nobody is joining (2.5 s, easing out to 12 s). Hosting and a friend joining now costs under twenty requests for a whole session, against roughly a hundred a minute before.

On top of that there are three relay hosts instead of one. If the first is blocked or rate limiting, the game silently moves to the next and remembers which one answered. When they all fail, the message now names the real reason — rate limited, timed out, or blocked — instead of blaming your wifi, and **Test my connection** reports each host separately.

## The bark

The dog barks with a real recording: four single barks taken from a freesound clip (`dog-barking-70772`), trimmed, levelled and laid end to end in half second slots inside one 15 KB mp3, embedded in the page so the game stays a single file that works offline.

The game never plays the same bark twice in a row, pitches each one a little differently so a series never sounds copied and pasted, pitches the alert burst higher than a calm one, and pans and fades it by where the dog is standing. Barks in a burst overlap, so the bark bus runs through a limiter: a four bark alert at point blank peaks at about half of full scale with nothing clipped.

If the clip ever fails to decode, the synthesised bark is still there as a fallback: a hard 7 ms attack, a pitch snapping up to 1.45x and falling to 0.6x, three vocal tract resonances and jitter on the folds.

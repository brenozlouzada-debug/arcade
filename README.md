# 3D Shooter

A first-person shooter that runs in the browser, written with three.js.

## Play it in Google Chrome

1. Download `shooter-standalone.html` (open it on GitHub and use **Download raw file**, or clone the repo).
2. Double-click it, or drag it into a Chrome window. It needs no internet connection and no server.
3. Click **Survival** or **Free Play**. Chrome captures the mouse when the game starts; press `Esc` to release it.

`shooter.html` is the same game but loads three.js from a CDN, so it needs a connection.

## Play online with friends

The host picks a mode before pressing Start: **Deathmatch** (free for all, the original) or **Co-op: fight the enemies together**, where everyone is on the same team against waves of soldiers. In co-op the host runs the enemies and everyone sees and shoots the same ones; enemy bullets hurt everyone, there is no friendly fire, and each player scores the kills they make. Waves get bigger with more players.

Up to 4 players, free-for-all arena (shoot, build, loot chests; most eliminations wins). It uses peer-to-peer WebRTC, so there is no server and no account. You swap two short codes in any chat app:

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

## Why online play said there was no internet

On the published site, hosting a game used to burn through the public code relay's allowance in about a minute: the host posted three seat offers, then polled three separate topics every two seconds, roughly ninety requests a minute from one address. ntfy.sh rate limits anonymous traffic, so it started answering 429 and every call after that failed with "check your internet". On the claude.ai copy this never showed, because that copy signals through its own database first and only falls back to the relay.

The relay protocol now uses two shared topics for a whole room instead of six, polls once per cycle, and slows down while nobody is joining (2.5 s, easing out to 12 s). Hosting and a friend joining now costs under twenty requests for a whole session, against roughly a hundred a minute before.

On top of that there are three relay hosts instead of one. If the first is blocked or rate limiting, the game silently moves to the next and remembers which one answered. When they all fail, the message now names the real reason — rate limited, timed out, or blocked — instead of blaming your wifi, and **Test my connection** reports each host separately.

## The bark

The dog barks with a real recording: four single barks taken from a freesound clip (`dog-barking-70772`), trimmed, levelled and laid end to end in half second slots inside one 15 KB mp3, embedded in the page so the game stays a single file that works offline.

The game never plays the same bark twice in a row, pitches each one a little differently so a series never sounds copied and pasted, pitches the alert burst higher than a calm one, and pans and fades it by where the dog is standing. Barks in a burst overlap, so the bark bus runs through a limiter: a four bark alert at point blank peaks at about half of full scale with nothing clipped.

If the clip ever fails to decode, the synthesised bark is still there as a fallback: a hard 7 ms attack, a pitch snapping up to 1.45x and falling to 0.6x, three vocal tract resonances and jitter on the folds.

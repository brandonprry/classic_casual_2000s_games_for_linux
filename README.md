# Wine-Bundled Casual Game AppImages

Self-contained Linux **AppImages** of 250 classic mid-2000s casual games. Each AppImage bundles its own copy of Wine plus the game, so it runs on any modern x86-64 Linux desktop with no system Wine required.

No internet required. No in-app purchases. 

```
https://drive.google.com/drive/folders/1SUSkwc0En0y8hxP1E4OuPWUBjnQmxu2_?usp=sharing
```

On first launch an AppImage builds a private, writable Wine prefix under `~/.local/share/play101/<game>/` (so saves and high scores persist) and copies the game into it; later launches start straight away.

```bash
chmod +x 'Alien_Outbreak_2_Invasion.AppImage'
./Alien_Outbreak_2_Invasion.AppImage
```

Extra launch arguments:

- `--winecfg` — open `winecfg` for that game's prefix
- `--wine <command>` — run an arbitrary Wine command in that game's prefix

## Display scaling with gamescope

These games render at a fixed low resolution (typically 800x600 or 1024x768) baked into the executable. To fill a modern display crisply, each AppImage can run the game through [**gamescope**](https://github.com/ValveSoftware/gamescope), which upscales the fixed-resolution output to your screen (FSR by default) with no monitor mode-switch.

Install gamescope from your distribution, e.g.:

```bash
sudo apt install gamescope   # Debian/Ubuntu
```

When gamescope is on your `PATH`, games run through it **by default**. Behaviour is controlled by two environment variables:

| Variable | Default | Description |
| --- | --- | --- |
| `PLAY101_GAMESCOPE` | `1` (auto) | Use gamescope when it is on `PATH`. Set to `0` or `off` to disable and run plain Wine. If gamescope is not installed, the game runs normally regardless. |
| `PLAY101_GAMESCOPE_FLAGS` | `-f -F fsr` | Flags passed to gamescope. `-f` = fullscreen, `-F fsr` = AMD FSR upscaling. |

Examples:

```bash
# Default: fullscreen, FSR upscaling (gamescope auto-detected)
./Action_Ball_2.AppImage

# Disable gamescope for this launch
PLAY101_GAMESCOPE=0 ./Action_Ball_2.AppImage

# Pixel-perfect integer scaling instead of FSR
PLAY101_GAMESCOPE_FLAGS="-f -S integer" ./Action_Ball_2.AppImage

# Force a specific output resolution
PLAY101_GAMESCOPE_FLAGS="-f -F fsr -W 2560 -H 1440" ./Action_Ball_2.AppImage
```

### Other environment variables

| Variable | Default | Description |
| --- | --- | --- |
| `PLAY101_PREFIX` | `~/.local/share/play101/<game>` | Override the Wine prefix location for the game. |
| `WINEDEBUG` | `-all` | Wine debug channels (set e.g. `+err` to troubleshoot). |

## Platform note

All 250 titles run on native x86-64 Linux. 

## Games (250)

Total download size: **106.97 GB** across 250 AppImages.

| Game | File | Size | Description |
| --- | --- | --- | --- |
| 100+ Great Games | `100_Great_Games.AppImage` | 495 MB | Compilation of over 100 casual arcade, puzzle, and card games. |
| 100+ Vol2 | `100_Vol2.AppImage` | 495 MB | Second-volume compilation of over 100 casual games. |
| 100,000 Mahjongg Games | `100000_Mahjongg_Games.AppImage` | 405 MB | Huge collection of Mahjong solitaire tile-matching layouts. |
| 1001 Japanese Crosswords | `1001_Japanese_Crosswords.AppImage` | 412 MB | 1001 nonogram (Picross) picture-logic puzzles. |
| 1001 Minigolf Challenge | `1001_Minigolf_Challenge.AppImage` | 422 MB | 1001 miniature-golf holes to putt through. |
| 1001 Nights - The Adventures Of Sindbad | `1001_Nights_-_The_Adventures_Of_Sindbad.AppImage` | 433 MB | Match-3 puzzle adventure through the Arabian Nights tales. |
| 1001 Tangram Puzzles | `1001_Tangram_Puzzles.AppImage` | 401 MB | 1001 tangram shape-forming puzzles. |
| 200+ Game Pack | `200_Game_Pack.AppImage` | 581 MB | Compilation of over 200 casual games. |
| 2002 Games | `2002_Games.AppImage` | 808 MB | Compilation of 2002 casual mini-games. |
| 2002 Kakuro Puzzles | `2002_Kakuro_Puzzles.AppImage` | 410 MB | 2002 Kakuro cross-sums number-logic puzzles. |
| 2002 Pentamino Puzzles | `2002_Pentamino_Puzzles.AppImage` | 403 MB | 2002 pentomino tile-fitting puzzles. |
| 2002 SpaceOut Games | `2002_SpaceOut_Games.AppImage` | 414 MB | Collection of space-themed brick-breaker arcade games. |
| 203GamePack | `203GamePack.AppImage` | 776 MB | Compilation of 203 casual games. |
| 3000 Jigsaw Puzzle Games | `3000_Jigsaw_Puzzle_Games.AppImage` | 1013 MB | 3000 digital jigsaw puzzles. |
| 3003 Crystal Mazes | `3003_Crystal_Mazes.AppImage` | 411 MB | 3003 crystal-themed maze puzzles. |
| 4500 Vegas Slots Bonus Bonanza | `4500_Vegas_Slots_Bonus_Bonanza.AppImage` | 409 MB | 4500 Vegas-style slot-machine games. |
| 500 Solitaire Games | `500_Solitaire_Games.AppImage` | 408 MB | 500 variations of solitaire card games. |
| Action Ball 2 | `Action_Ball_2.AppImage` | 411 MB | Arkanoid-style brick-breaker with power-ups and bosses. |
| Action Ball Deluxe | `Action_Ball_Deluxe.AppImage` | 408 MB | Breakout/Arkanoid brick-breaking arcade game. |
| Airball | `Airball.AppImage` | 404 MB | Arcade ball-rolling maze game. |
| Airball2 | `Airball2.AppImage` | 408 MB | Sequel arcade ball-rolling maze game. |
| Alabama Smith in Escape from Pompeii | `Alabama_Smith_in_Escape_from_Pompeii.AppImage` | 466 MB | Hidden-object puzzle adventure with a globe-trotting explorer. |
| Alabama Smith in the Quest of Fate | `Alabama_Smith_in_the_Quest_of_Fate.AppImage` | 529 MB | Hidden-object adventure following explorer Alabama Smith. |
| Alchemy Drop | `Alchemy_Drop.AppImage` | 402 MB | Tile-matching alchemy puzzle game. |
| Alex Gordon | `Alex_Gordon.AppImage` | 427 MB | Side-scrolling platformer about a hero collecting gems. |
| Alexandra Fortune - Mystery of the Lunar Archipelago | `Alexandra_Fortune_-_Mystery_of_the_Lunar_Archipelago.AppImage` | 592 MB | Hidden-object mystery adventure. |
| Alien Outbreak 2 Invasion | `Alien_Outbreak_2_Invasion.AppImage` | 410 MB | Top-down arcade space shooter against alien swarms. |
| Amelie's Café | `Amelies_Cafe.AppImage` | 446 MB | Time-management game running a busy café. |
| Amelie's Café Holiday Spirit | `Amelies_Cafe_Holiday_Spirit.AppImage` | 527 MB | Holiday-themed café time-management game. |
| Amelie's Café Summer Time | `Amelies_Cafe_Summer_Time.AppImage` | 483 MB | Summer-themed café time-management game. |
| AquaBoat Maze | `AquaBoat_Maze.AppImage` | 409 MB | Navigate a boat through aquatic mazes. |
| Aquamania | `Aquamania.AppImage` | 403 MB | Fast-paced aquatic action puzzle game. |
| AquariumShop | `AquariumShop.AppImage` | 432 MB | Time-management game running an aquarium shop. |
| ArcaPinball Wacky Worlds | `ArcaPinball_Wacky_Worlds.AppImage` | 416 MB | Arcade pinball with whimsical themed tables. |
| ArcaPinballNeoWorlds | `ArcaPinballNeoWorlds.AppImage` | 414 MB | Arcade pinball with futuristic themed tables. |
| Arctic Quest | `Arctic_Quest.AppImage` | 416 MB | Match-3 puzzle game with an arctic theme. |
| Arctic Quest 2 | `Arctic_Quest_2.AppImage` | 417 MB | Arctic-themed match-3 puzzle sequel. |
| Astro Color Twist | `Astro_Color_Twist.AppImage` | 407 MB | Color-matching arcade puzzle with a space theme. |
| AtomBall | `AtomBall.AppImage` | 401 MB | Arcade brick-and-ball game with an atomic theme. |
| AtomBomber | `AtomBomber.AppImage` | 403 MB | Arcade action bombing game. |
| Aztec Tribe | `Aztec_Tribe.AppImage` | 454 MB | Resource-management strategy game building an Aztec settlement. |
| Aztec Tribe - New Land | `Aztec_Tribe_-_New_Land.AppImage` | 466 MB | Strategy city-building sequel set in Aztec times. |
| Baby Bird Care | `Baby_Bird_Care.AppImage` | 424 MB | Pet-care time-management game raising baby birds. |
| Backgammon3D | `Backgammon3D.AppImage` | 406 MB | 3D backgammon board game. |
| Beach Party Craze | `Beach_Party_Craze.AppImage` | 441 MB | Time-management game running a beach resort. |
| Bilbo - The Four Corners of the World | `Bilbo_-_The_Four_Corners_of_the_World.AppImage` | 436 MB | Hidden-object adventure across exotic locales. |
| Billiards Champ 3D | `Billiards_Champ_3D.AppImage` | 410 MB | 3D billiards and pool simulation. |
| Book Tales | `Book_Tales.AppImage` | 415 MB | Hidden-object adventure set in storybook worlds. |
| Breakball Lost In Space | `Breakball_Lost_In_Space.AppImage` | 404 MB | Space-themed brick-breaker (Breakout) game. |
| BreakballTimeTravel | `BreakballTimeTravel.AppImage` | 411 MB | Time-travel-themed brick-breaker game. |
| Bug Frenzy | `Bug_Frenzy.AppImage` | 406 MB | Fast-paced insect-themed arcade puzzle game. |
| BulldozerBob | `BulldozerBob.AppImage` | 411 MB | Block-pushing puzzle game driving a bulldozer. |
| Business Boardwalk | `Business_Boardwalk.AppImage` | 408 MB | Property and business tycoon board game. |
| Bustout 3D Worlds | `Bustout_3D_Worlds.AppImage` | 408 MB | 3D Breakout brick-breaking game. |
| Carl the Caveman | `Carl_the_Caveman.AppImage` | 420 MB | Puzzle-platformer about a caveman digging for treasure. |
| Championship Chess | `Championship_Chess.AppImage` | 405 MB | Chess game with tournament play. |
| Checkers 3D | `Checkers_3D.AppImage` | 402 MB | 3D checkers (draughts) board game. |
| Chess Brain Teasers 100K | `Chess_Brain_Teasers_100K.AppImage` | 402 MB | Collection of 100,000 chess puzzles and brain teasers. |
| Chess Magic 30K | `Chess_Magic_30K.AppImage` | 403 MB | Collection of 30,000 chess puzzles. |
| Chess Reversi 100K | `Chess_Reversi_100K.AppImage` | 403 MB | Collection of 100,000 Reversi/Othello board puzzles. |
| Chess Solitaire 50K | `Chess_Solitaire_50K.AppImage` | 403 MB | Collection of 50,000 chess-solitaire puzzles. |
| Chess Sudoku 100K | `Chess_Sudoku_100K.AppImage` | 403 MB | Collection of 100,000 chess-themed Sudoku puzzles. |
| ChineseChessDeluxe | `ChineseChessDeluxe.AppImage` | 401 MB | Chinese chess (Xiangqi) board game. |
| Circular Pool | `Circular_Pool.AppImage` | 403 MB | Billiards played on a circular table. |
| City Magnate | `City_Magnate.AppImage` | 409 MB | City-building economic strategy game. |
| CosmoAlley Bowling | `CosmoAlley_Bowling.AppImage` | 408 MB | Space-themed ten-pin bowling game. |
| Crop Busters | `Crop_Busters.AppImage` | 479 MB | Farming-themed match-3 puzzle game. |
| Crusaders Of Space 2 | `Crusaders_Of_Space_2.AppImage` | 413 MB | Top-down arcade space shooter. |
| CrypticCastle | `CrypticCastle.AppImage` | 410 MB | Hidden-object puzzle adventure in a mysterious castle. |
| Crystal Caverns of AmonRa | `Crystal_Caverns_of_AmonRa.AppImage` | 426 MB | Egyptian-themed arcade puzzle game. |
| CrystalIceQuest | `CrystalIceQuest.AppImage` | 423 MB | Ice-themed match-3 puzzle game. |
| Cubic Frenzy | `Cubic_Frenzy.AppImage` | 430 MB | Block-matching arcade puzzle game. |
| Dancing Craze | `Dancing_Craze.AppImage` | 479 MB | Rhythm and dance arcade game. |
| DeepSeaMarblePop | `DeepSeaMarblePop.AppImage` | 419 MB | Undersea marble-popping (Zuma-style) puzzle. |
| Digger Adventures | `Digger_Adventures.AppImage` | 413 MB | Dig-and-collect arcade game in the Boulder Dash style. |
| Diner Drop LE | `Diner_Drop_LE.AppImage` | 404 MB | Chain-reaction matching puzzle with a diner theme. |
| Doctors Lab | `Doctors_Lab.AppImage` | 402 MB | Laboratory-themed matching puzzle game. |
| Dragon Puzzle | `Dragon_Puzzle.AppImage` | 407 MB | Dragon-themed tile-matching puzzle. |
| Dynasty of Egypt | `Dynasty_of_Egypt.AppImage` | 428 MB | Egyptian-themed match-3 and building puzzle. |
| Enchanted Cavern | `Enchanted_Cavern.AppImage` | 422 MB | Match-3 puzzle in a gem-filled cavern. |
| Enchanted Words | `Enchanted_Words.AppImage` | 405 MB | Word-building puzzle game with a fantasy theme. |
| Extreme Motorbike Racing | `Extreme_Motorbike_Racing.AppImage` | 499 MB | Arcade motorcycle racing game. |
| Extreme Riverboat Racing | `Extreme_Riverboat_Racing.AppImage` | 457 MB | Arcade riverboat racing game. |
| Fairy Tale Quest | `Fairy_Tale_Quest.AppImage` | 419 MB | Fairy-tale-themed match-3 puzzle adventure. |
| FairyFlowerVines | `FairyFlowerVines.AppImage` | 426 MB | Puzzle game growing magical flower vines. |
| FairyTaleQuest | `FairyTaleQuest.AppImage` | 419 MB | Fairy-tale-themed puzzle adventure. |
| Farmer Crates | `Farmer_Crates.AppImage` | 407 MB | Stacking and sorting puzzle on a farm. |
| Fashion Craze | `Fashion_Craze.AppImage` | 442 MB | Time-management game running a fashion boutique. |
| Fashion Season | `Fashion_Season.AppImage` | 420 MB | Fashion-boutique time-management game. |
| Fast Food Mania | `Fast_Food_Mania.AppImage` | 408 MB | Fast-food restaurant time-management game. |
| Finding Doggy | `Finding_Doggy.AppImage` | 419 MB | Hidden-object search game to find a lost dog. |
| Fish Food LE | `Fish_Food_LE.AppImage` | 402 MB | Feed-the-fish arcade action game. |
| Fishing Frenzy | `Fishing_Frenzy.AppImage` | 406 MB | Fast-paced fishing arcade game. |
| Flower Garden Tycoon | `Flower_Garden_Tycoon.AppImage` | 430 MB | Gardening business and tycoon game. |
| Flower Quest | `Flower_Quest.AppImage` | 413 MB | Match-3 puzzle with a floral theme. |
| FlowersinBloom | `FlowersinBloom.AppImage` | 409 MB | Flower-matching puzzle game. |
| Flybot | `Flybot.AppImage` | 410 MB | Arcade flying-robot action game. |
| Foosball Champ 3D | `Foosball_Champ_3D.AppImage` | 407 MB | 3D table-football (foosball) game. |
| FourUp | `FourUp.AppImage` | 400 MB | Connect Four style strategy game. |
| Froggy's Adventures | `Froggys_Adventures.AppImage` | 414 MB | Frogger-style arcade hopping game. |
| Fruit Lockers 2 - The Enchanting Islands | `Fruit_Lockers_2_-_The_Enchanting_Islands.AppImage` | 438 MB | Match-3 puzzle adventure across tropical islands. |
| GardenLand Tycoon | `GardenLand_Tycoon.AppImage` | 435 MB | Garden and park business tycoon game. |
| Gems of Amazon | `Gems_of_Amazon.AppImage` | 406 MB | Amazon-themed match-3 gem puzzle. |
| Gems of the Amazon | `Gems_of_the_Amazon.AppImage` | 406 MB | Amazon-themed match-3 gem puzzle. |
| Gerbil Drop | `Gerbil_Drop.AppImage` | 402 MB | Physics chain-reaction puzzle with gerbils. |
| GhostlyGarden | `GhostlyGarden.AppImage` | 410 MB | Spooky-themed matching and hidden-object puzzle. |
| Gold Runner | `Gold_Runner.AppImage` | 404 MB | Lode Runner-style platform puzzle collecting gold. |
| Gourmania | `Gourmania.AppImage` | 468 MB | Cooking and restaurant time-management game. |
| Gourmania 2 - Kitchen Confidential | `Gourmania_2_-_Kitchen_Confidential.AppImage` | 681 MB | Cooking time-management sequel. |
| Gourmania 3 - Zoo Zoom | `Gourmania_3_-_Zoo_Zoom.AppImage` | 518 MB | Zoo-restaurant cooking time-management game. |
| Grand Master Chess Online | `Grand_Master_Chess_Online.AppImage` | 424 MB | Chess game with online play. |
| Hamlet | `Hamlet.AppImage` | 483 MB | Comic puzzle-adventure parody of Shakespeare's Hamlet. |
| Haunted Domains | `Haunted_Domains.AppImage` | 440 MB | Hidden-object game across haunted locations. |
| HauntedHotel | `HauntedHotel.AppImage` | 410 MB | Hidden-object mystery set in a haunted hotel. |
| HeliQuick Bob | `HeliQuick_Bob.AppImage` | 408 MB | Helicopter arcade delivery game. |
| Heroes Of Hellas | `Heroes_Of_Hellas.AppImage` | 418 MB | Match-3 puzzle set in ancient Greece. |
| Heroes of Hellas 2 - Olympia | `Heroes_of_Hellas_2_-_Olympia.AppImage` | 487 MB | Greek-mythology match-3 puzzle sequel. |
| Hexagon Mahjongg | `Hexagon_Mahjongg.AppImage` | 420 MB | Mahjong solitaire on hexagonal layouts. |
| Hidden Object Collection | `Hidden_Object_Collection.AppImage` | 455 MB | Compilation of hidden-object searching scenes. |
| Hidden Object Mania | `Hidden_Object_Mania.AppImage` | 466 MB | Hidden-object searching game. |
| Hidden World | `Hidden_World.AppImage` | 542 MB | Hidden-object adventure game. |
| Holiday Rush | `Holiday_Rush.AppImage` | 418 MB | Holiday-themed time-management game. |
| Holly - A Christmas Tale | `Holly_-_A_Christmas_Tale.AppImage` | 451 MB | Christmas-themed match-3 puzzle adventure. |
| Holly 2 - Magic Land | `Holly_2_-_Magic_Land.AppImage` | 441 MB | Match-3 puzzle adventure sequel. |
| Hotel Mogul | `Hotel_Mogul.AppImage` | 478 MB | Build-and-manage hotel time-management game. |
| Hunt for Treasure | `Hunt_for_Treasure.AppImage` | 502 MB | Hidden-object treasure-hunting game. |
| Hyperballoid 2 | `Hyperballoid_2.AppImage` | 434 MB | Breakout/Arkanoid brick-breaker sequel. |
| Hyperspace Invader | `Hyperspace_Invader.AppImage` | 412 MB | Space Invaders-style arcade shooter. |
| Island Maze Escape | `Island_Maze_Escape.AppImage` | 406 MB | Maze-navigation escape puzzle set on an island. |
| Island Realms | `Island_Realms.AppImage` | 439 MB | Island city-building strategy game. |
| Jail Runner | `Jail_Runner.AppImage` | 410 MB | Arcade running and escape game. |
| Jenny's Fish Shop | `Jennys_Fish_Shop.AppImage` | 431 MB | Fish-shop time-management game. |
| Jewel Mines LE | `Jewel_Mines_LE.AppImage` | 403 MB | Gem-mining match-3 puzzle. |
| Jewel Wizardry | `Jewel_Wizardry.AppImage` | 411 MB | Fantasy match-3 jewel puzzle. |
| Jewels of the Nile | `Jewels_of_the_Nile.AppImage` | 425 MB | Egyptian-themed match-3 jewel puzzle. |
| Joan Jade and the Gates of Xibalba | `Joan_Jade_and_the_Gates_of_Xibalba.AppImage` | 479 MB | Hidden-object adventure with an adventuring heroine. |
| Journey of Hope | `Journey_of_Hope.AppImage` | 569 MB | Match-3 puzzle adventure. |
| Juliette's Fashion Empire | `Juliettes_Fashion_Empire.AppImage` | 444 MB | Fashion-business time-management game. |
| King Solomons Lost Mines | `King_Solomons_Lost_Mines.AppImage` | 408 MB | Match-3 adventure through lost mines. |
| KlondikeSolitaireGold | `KlondikeSolitaireGold.AppImage` | 408 MB | Klondike solitaire card game. |
| Land of Runes | `Land_of_Runes.AppImage` | 425 MB | Match-3 puzzle with a runic fantasy theme. |
| LilHerder | `LilHerder.AppImage` | 410 MB | Animal-herding arcade puzzle game. |
| Lovely Kitchen | `Lovely_Kitchen.AppImage` | 467 MB | Cooking time-management game. |
| Luftwaffe Airstrike LE | `Luftwaffe_Airstrike_LE.AppImage` | 403 MB | World War II aerial arcade shooter. |
| Magic Encyclopedia - First Story | `Magic_Encyclopedia_-_First_Story.AppImage` | 474 MB | Hidden-object mystery adventure. |
| Magic Shop | `Magic_Shop.AppImage` | 417 MB | Time-management game running a magic shop. |
| Magic Spheres | `Magic_Spheres.AppImage` | 410 MB | Marble-popping (Zuma-style) puzzle game. |
| Magin Encyclopedia - Moon Light | `Magin_Encyclopedia_-_Moon_Light.AppImage` | 484 MB | Hidden-object mystery adventure sequel. |
| Maginmons | `Maginmons.AppImage` | 404 MB | Monster-themed matching puzzle game. |
| Mahjongg Artifacts | `Mahjongg_Artifacts.AppImage` | 412 MB | Mahjong solitaire adventure. |
| Mahjongg Artifacts 2 | `Mahjongg_Artifacts_2.AppImage` | 414 MB | Mahjong solitaire adventure sequel. |
| MegaPinball | `MegaPinball.AppImage` | 413 MB | Arcade pinball game. |
| Millennium Gamepak Gold | `Millennium_Gamepak_Gold.AppImage` | 434 MB | Large compilation of casual games (Gold edition). |
| Millennium Gamepak Platinum | `Millennium_Gamepak_Platinum.AppImage` | 545 MB | Large compilation of casual games (Platinum edition). |
| MiniGolfMania | `MiniGolfMania.AppImage` | 404 MB | Miniature-golf arcade game. |
| Monster Doors | `Monster_Doors.AppImage` | 405 MB | Monster-themed arcade puzzle game. |
| Monster House | `Monster_House.AppImage` | 419 MB | Hidden-object puzzle set in a monster-filled house. |
| Monster Truck Stunt Rally | `Monster_Truck_Stunt_Rally.AppImage` | 409 MB | Monster-truck stunt racing game. |
| Monster Village | `Monster_Village.AppImage` | 419 MB | Monster-themed building and matching game. |
| Montezumas Quest | `Montezumas_Quest.AppImage` | 417 MB | Aztec-themed match-3 puzzle adventure. |
| Muncher Mania Classic LE | `Muncher_Mania_Classic_LE.AppImage` | 403 MB | Pac-Man-style maze muncher arcade game. |
| My Farm Life | `My_Farm_Life.AppImage` | 448 MB | Farm time-management game. |
| Mysteries of Horus | `Mysteries_of_Horus.AppImage` | 409 MB | Egyptian-themed match-3 puzzle. |
| Mystery Cookbook | `Mystery_Cookbook.AppImage` | 420 MB | Cooking-themed hidden-object puzzle game. |
| Mystery Moscow | `Mystery_Moscow.AppImage` | 406 MB | Hidden-object mystery set in Moscow. |
| Mystery NewYork | `Mystery_NewYork.AppImage` | 406 MB | Hidden-object mystery set in New York. |
| Mystery Paris | `Mystery_Paris.AppImage` | 406 MB | Hidden-object mystery set in Paris. |
| MysteryLondon | `MysteryLondon.AppImage` | 412 MB | Hidden-object mystery set in London. |
| MysteryMuseum | `MysteryMuseum.AppImage` | 410 MB | Hidden-object mystery set in a museum. |
| Mystic Diamonds | `Mystic_Diamonds.AppImage` | 407 MB | Match-3 diamond puzzle game. |
| MysticStore | `MysticStore.AppImage` | 416 MB | Mystic-themed shop time-management game. |
| Natalie Brooks - Secrets of the Treasure House | `Natalie_Brooks_-_Secrets_of_the_Treasure_House.AppImage` | 440 MB | Hidden-object adventure mystery. |
| Natalie Brooks - Treasures of the Lost Kingdom | `Natalie_Brooks_-_Treasures_of_the_Lost_Kingdom.AppImage` | 489 MB | Hidden-object adventure mystery sequel. |
| Oriental Dreams | `Oriental_Dreams.AppImage` | 521 MB | Match-3 puzzle with an Asian theme. |
| Parking Lot Maze | `Parking_Lot_Maze.AppImage` | 407 MB | Car-parking and maze navigation puzzle. |
| PenguinPush | `PenguinPush.AppImage` | 406 MB | Sokoban-style block-pushing puzzle with penguins. |
| Pet Show Craze | `Pet_Show_Craze.AppImage` | 442 MB | Pet-show time-management game. |
| Pharaohs Challenge | `Pharaohs_Challenge.AppImage` | 413 MB | Egyptian-themed match and puzzle game. |
| Poker Drop | `Poker_Drop.AppImage` | 403 MB | Poker-themed chain-matching puzzle. |
| PowerPipes | `PowerPipes.AppImage` | 403 MB | Pipe-connecting logic puzzle game. |
| Puzzle & Board XP Championship | `Puzzle_Board_XP_Championship.AppImage` | 478 MB | Collection of classic puzzle and board games. |
| Pyramid Escape | `Pyramid_Escape.AppImage` | 408 MB | Egyptian maze and puzzle escape game. |
| Pyramid Solitaire Gold | `Pyramid_Solitaire_Gold.AppImage` | 407 MB | Pyramid solitaire card game. |
| Rescue Frenzy | `Rescue_Frenzy.AppImage` | 582 MB | Time-management rescue game. |
| Robotic Worlds | `Robotic_Worlds.AppImage` | 438 MB | Robot-themed arcade puzzle game. |
| RollerBall Fantasy Island | `RollerBall_Fantasy_Island.AppImage` | 408 MB | Pinball and ball-rolling arcade game. |
| Sea Bounty - Dead Man's Chest | `Sea_Bounty_-_Dead_Mans_Chest.AppImage` | 418 MB | Pirate-themed match-3 puzzle adventure. |
| Secret Empires Anasazi | `Secret_Empires_Anasazi.AppImage` | 433 MB | Hidden-object adventure set among the Anasazi. |
| Secret Empires Aztec | `Secret_Empires_Aztec.AppImage` | 433 MB | Hidden-object adventure set in the Aztec empire. |
| Secret Empires Inca | `Secret_Empires_Inca.AppImage` | 433 MB | Hidden-object adventure set in the Inca empire. |
| Secret Empires Maya | `Secret_Empires_Maya.AppImage` | 433 MB | Hidden-object adventure set in the Maya empire. |
| Seek and Find Collection 1 | `Seek_and_Find_Collection_1.AppImage` | 471 MB | Collection of hidden-object seek-and-find scenes. |
| Seek and Find Collection 2 | `Seek_and_Find_Collection_2.AppImage` | 471 MB | Collection of hidden-object seek-and-find scenes. |
| Sheep's Quest | `Sheeps_Quest.AppImage` | 447 MB | Puzzle-platformer guiding sheep to safety. |
| Ski Resort Mogul | `Ski_Resort_Mogul.AppImage` | 464 MB | Build-and-manage ski resort time-management game. |
| Sky Kingdoms | `Sky_Kingdoms.AppImage` | 440 MB | Match-3 building puzzle set in floating kingdoms. |
| Sky Taxi 4 | `Sky_Taxi_4.AppImage` | 532 MB | Arcade platformer piloting a flying taxi. |
| Snark Busters - All Revved Up | `Snark_Busters_-_All_Revved_Up.AppImage` | 694 MB | Hidden-object puzzle adventure. |
| Snark Busters - Welcome to the Club | `Snark_Busters_-_Welcome_to_the_Club.AppImage` | 604 MB | Hidden-object puzzle adventure. |
| Snowball Bustout | `Snowball_Bustout.AppImage` | 402 MB | Winter-themed Breakout brick-breaker. |
| Snowy - Fish Frenzy | `Snowy_-_Fish_Frenzy.AppImage` | 421 MB | Snowy the polar bear arcade fishing game. |
| Snowy - Lunch Rush | `Snowy_-_Lunch_Rush.AppImage` | 421 MB | Snowy the polar bear restaurant arcade game. |
| Snowy - Puzzle Islands | `Snowy_-_Puzzle_Islands.AppImage` | 406 MB | Snowy the polar bear puzzle game. |
| Snowy - Space Trip | `Snowy_-_Space_Trip.AppImage` | 410 MB | Snowy the polar bear space arcade game. |
| Snowy - The Bear's Adventures | `Snowy_-_The_Bears_Adventures.AppImage` | 411 MB | Side-scrolling platformer starring Snowy the polar bear. |
| Snowy - Treasure Hunter | `Snowy_-_Treasure_Hunter.AppImage` | 419 MB | Snowy the polar bear platform adventure. |
| Snowy - Treasure Hunter 2 | `Snowy_-_Treasure_Hunter_2.AppImage` | 420 MB | Snowy the polar bear platform adventure sequel. |
| SolitaireDozenGold | `SolitaireDozenGold.AppImage` | 408 MB | Collection of a dozen solitaire card games. |
| Space Crusaders | `Space_Crusaders.AppImage` | 414 MB | Top-down arcade space shooter. |
| Spider Solitaire Gold | `Spider_Solitaire_Gold.AppImage` | 408 MB | Spider solitaire card game. |
| Sprill - The Mystery of The Bermuda Triangle | `Sprill_-_The_Mystery_of_The_Bermuda_Triangle.AppImage` | 488 MB | Hidden-object puzzle adventure. |
| Sprill and Ritchie - Adventures in Time | `Sprill_and_Ritchie_-_Adventures_in_Time.AppImage` | 531 MB | Hidden-object time-travel adventure. |
| Spy Chaser | `Spy_Chaser.AppImage` | 406 MB | Arcade chase and action game. |
| Stand O'Food | `Stand_OFood.AppImage` | 407 MB | Fast-food restaurant time-management game. |
| Starcosmic Bustout LE | `Starcosmic_Bustout_LE.AppImage` | 401 MB | Space-themed Breakout brick-breaker. |
| Starcosmic Invaders LE | `Starcosmic_Invaders_LE.AppImage` | 403 MB | Space Invaders-style arcade shooter. |
| StoneAgeTaxi | `StoneAgeTaxi.AppImage` | 409 MB | Prehistoric taxi-driving arcade game. |
| Strike Ball 3 | `Strike_Ball_3.AppImage` | 425 MB | Arkanoid-style brick-breaker. |
| Strike Bowling | `Strike_Bowling.AppImage` | 409 MB | Ten-pin bowling game. |
| Sudoku Mania | `Sudoku_Mania.AppImage` | 418 MB | Collection of Sudoku number puzzles. |
| Summer Resort Mogul | `Summer_Resort_Mogul.AppImage` | 421 MB | Resort-building time-management game. |
| Sunshine Acres | `Sunshine_Acres.AppImage` | 435 MB | Farm and estate time-management game. |
| Super Fox | `Super_Fox.AppImage` | 433 MB | Side-scrolling arcade platformer. |
| Super Frog | `Super_Frog.AppImage` | 412 MB | Frogger-style arcade platformer. |
| Super Mole | `Super_Mole.AppImage` | 408 MB | Arcade mole-themed action game. |
| Super Word Games 10,000 | `Super_Word_Games_10000.AppImage` | 403 MB | Collection of 10,000 word puzzle games. |
| SuperFox2 | `SuperFox2.AppImage` | 445 MB | Side-scrolling arcade platformer sequel. |
| Supermarket Mania | `Supermarket_Mania.AppImage` | 443 MB | Supermarket time-management game. |
| Tank Battle | `Tank_Battle.AppImage` | 402 MB | Top-down tank combat arcade game. |
| Tapiei Mahjongg 25K | `Tapiei_Mahjongg_25K.AppImage` | 421 MB | Collection of 25,000 Taipei Mahjong solitaire layouts. |
| TeapotPoppers | `TeapotPoppers.AppImage` | 416 MB | Marble-popping bubble-shooter puzzle. |
| Tennis Championship | `Tennis_Championship.AppImage` | 417 MB | Arcade tennis game. |
| Texas Holdem 3D | `Texas_Holdem_3D.AppImage` | 413 MB | 3D Texas Hold'em poker game. |
| The Curse Of Montezuma | `The_Curse_Of_Montezuma.AppImage` | 436 MB | Aztec-themed match-3 puzzle. |
| The Enchanting Islands | `The_Enchanting_Islands.AppImage` | 435 MB | Match-3 island puzzle adventure. |
| The Joy of Farming | `The_Joy_of_Farming.AppImage` | 438 MB | Farm time-management game. |
| The Tahiti Hidden Pearls | `The_Tahiti_Hidden_Pearls.AppImage` | 442 MB | Tropical match-3 and hidden-object puzzle. |
| The Treasures Of Montezuma | `The_Treasures_Of_Montezuma.AppImage` | 436 MB | Aztec-themed match-3 puzzle game. |
| The Treasures Of Montezuma 2 | `The_Treasures_Of_Montezuma_2.AppImage` | 458 MB | Aztec-themed match-3 puzzle sequel. |
| Time Breaker | `Time_Breaker.AppImage` | 412 MB | Time-travel arcade puzzle game. |
| Tory's Shop'n'Rush | `Torys_ShopnRush.AppImage` | 420 MB | Shop-management time-management game. |
| Treasure Masters, Inc | `Treasure_Masters_Inc.AppImage` | 502 MB | Hidden-object puzzle adventure. |
| Tropical Farm | `Tropical_Farm.AppImage` | 434 MB | Tropical farm time-management game. |
| Turtix | `Turtix.AppImage` | 445 MB | Side-scrolling platformer starring a turtle hero. |
| Turtix - Rescue Adventure | `Turtix_-_Rescue_Adventure.AppImage` | 425 MB | Side-scrolling turtle platformer sequel. |
| Ultimate Gamepak | `Ultimate_Gamepak.AppImage` | 454 MB | Large compilation of casual games. |
| Vacation Mogul | `Vacation_Mogul.AppImage` | 437 MB | Property and resort time-management game. |
| VogueTales | `VogueTales.AppImage` | 425 MB | Fashion-themed time-management game. |
| VolcanicBlocks | `VolcanicBlocks.AppImage` | 427 MB | Volcano-themed block-matching puzzle. |
| WWII Aerial Dogfight | `WWII_Aerial_Dogfight.AppImage` | 405 MB | World War II aerial combat arcade shooter. |

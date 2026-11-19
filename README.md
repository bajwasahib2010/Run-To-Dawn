=====================================================================
                          RUN TO DAWN
                        by MAXIMUS LARPUS
=====================================================================

Something is hunting you. Run through eight nightmare levels, from a
burning village to the road to dawn, and reach the chapel before the
monsters catch you.

Run To Dawn is a 2D auto-runner with pixel art, a full soundtrack,
unlockable characters, three difficulty levels and an endless
Free Play mode.


---------------------------------------------------------------------
 HOW TO PLAY
---------------------------------------------------------------------

Your character runs automatically. You only have to jump.

  JUMP ................ SPACE, UP ARROW, W, left mouse click, or tap
  PAUSE ............... ESC or P
  MUTE / UNMUTE ....... M (works anywhere in the game)
  MENUS ............... mouse / touch

The rules:

  * A monster chases you the whole way.
  * Hitting an obstacle makes you stumble and slow down, so the
    monster catches up. Each hit costs you a heart.
  * Get caught, or lose all your hearts, and the level restarts.
  * Bounce pads launch you into the air and give a short speed boost.
  * Reach the chapel at the end of the level to escape.
  * Each level is timed. Your best times are saved on the Leaderboard.
  * A red danger bar and war-drums warn you when a monster is close.
    Recover from a stumble and the drums fade away.


---------------------------------------------------------------------
 THE LEVELS
---------------------------------------------------------------------

  1  The Village           Hellhound
  2  The Forest            Hellhound, Vampire
  3  The Monastery         Vampire, Werewolf
  4  The Catacombs         Wraith, Hellhound, Vampire
  5  The Swamp             Werewolf, Wraith, Hellhound
  6  The Burning Pass      Demon, Werewolf, Vampire
  7  The Gates of Hell     Demon, Wraith, Hellhound, Vampire
  8  The Road to Dawn      Demon, Werewolf, Wraith, Vampire

Levels get longer, the obstacles get more crowded, and the monsters
get stronger as you go.

The monsters:

  HELLHOUND   Lunges at you once it gets strong enough.
  VAMPIRE     Lunges at you from the start.
  WEREWOLF    Speeds up the longer the level lasts.
  WRAITH      Teleports forward in short jumps.
  DEMON       Biggest reach, lunges, and goes into a frenzy.


---------------------------------------------------------------------
 DIFFICULTY
---------------------------------------------------------------------

  EASY     5 hearts. Slower monsters, fewer obstacles, more bounce
           pads, bigger head start.
  NORMAL   3 hearts. The standard experience.
  HARD     2 hearts. Relentless monsters, a crowded track, few bounce
           pads.

Clear every level on HARD to unlock the legendary Maximus.


---------------------------------------------------------------------
 CHARACTERS
---------------------------------------------------------------------

  ELIAS     FAST        Runs quickest.
  VICTOR    HIGH JUMP   Clears anything.
  LUCIAN    TOUGH       Barely slows down when hit.

Unlockable:

  SELENE    BALANCED    Good at everything.
                        Unlock: clear 2 levels.
  DANTE     SPRINTER    Fastest, but fragile.
                        Unlock: clear 4 levels.
  MIRA      ACROBAT     Leaps over anything.
                        Unlock: clear 6 levels.
  MAXIMUS   LEGEND      Best at everything.
                        Unlock: clear every level on Hard.


---------------------------------------------------------------------
 GAME MODES AND MENUS
---------------------------------------------------------------------

  PLAY          Story mode through all eight levels. Your total time
                is shown on the Ending screen.
  FREE PLAY     Endless run. There is no chapel and no finish line.
                The run only ends when you die. New monsters appear
                the further you go. Your best distance is saved.
  LEADERBOARD   Best times per level and difficulty, lifetime stats,
                and how your recent runs compare to earlier ones.
  OPTIONS       Master, Music and Sound Effects volume in 10% steps.
                Your settings are remembered between sessions.
  QUIT          Exit the game.

Cheats (pause menu): Unlimited Health, Speed Boost, Jump Boost.
Runs played with any cheat on are NOT saved to the leaderboard.

Your progress, unlocks, times and settings are saved automatically.


---------------------------------------------------------------------
 WHAT'S IN THE DOWNLOAD
---------------------------------------------------------------------

  RunToDawn_WINDOWS_.zip   Windows build
  RunToDawn_LINUX_.zip     Linux build (64-bit)
  RunToDawnmac.zip         macOS build
  web.zip                  Browser (HTML5 / WebAssembly) build
  RunToDawn_.zip           Full Godot project source


---------------------------------------------------------------------
 HOW TO RUN IT
---------------------------------------------------------------------

WINDOWS
  1. Unzip RunToDawn_WINDOWS_.zip. Keep all three files together.
  2. Double-click RunToDawnwin.exe.
  (RunToDawnwin.console.exe does the same thing but also opens a
  console window showing game logs. Handy if something goes wrong.)
  If Windows SmartScreen warns you, click "More info", then
  "Run anyway".

MACOS
  1. Unzip RunToDawnmac.zip.
  2. Double-click RunToDawn.app.
  If macOS says the app can't be opened because it is from an
  unidentified developer, right-click (or Control-click) the app,
  choose Open, then confirm. You only have to do this once.
  You can also launch it from Terminal with RunToDawn.command.

LINUX
  1. Unzip RunToDawn_LINUX_.zip. Keep all three files together.
  2. Make the files executable:
         chmod +x RunToDawnlin.sh RunToDawnlin.x86_64
  3. Run ./RunToDawnlin.sh (or ./RunToDawnlin.x86_64 directly).

WEB BUILD
  1. Unzip web.zip. The files must stay together in one folder.
  2. Browsers will not run WebAssembly games from a file:// address,
     so serve the folder with a local web server, for example:
         python3 -m http.server 8000
     then open http://localhost:8000 in your browser.
  3. To publish it online, upload every file in the folder to any
     static web host (itch.io, GitHub Pages, Netlify, etc.) and make
     sure index.html is at the top level.
  Use a modern browser (Chrome, Edge, Firefox, Safari). Click the
  game once if the audio does not start; browsers block sound until
  you interact with the page.

NOTE: Every build needs its .pck data file next to the executable
(RunToDawn*.pck on Windows, Linux and web; it is inside the .app on
macOS). Do not move or delete it.


---------------------------------------------------------------------
 OPENING THE PROJECT IN GODOT (for developers)
---------------------------------------------------------------------

  1. Install Godot 4.7 (the project was made with the 4.7 feature
     set; the original notes say 4.3+).
  2. Open the Godot Project Manager, click Import, pick project.godot
     in the RunToDawn folder, then Import & Edit.
  3. Press F5 to play.

  Renderer: Compatibility (GL), 1280x720 window, canvas_items
  stretch, nearest-neighbour texture filtering for crisp pixel art.

Project layout:

  Scenes/    Intro, MainMenu, Difficulty, CharacterSelect, Level,
             Ending, Credits, Leaderboard
  Scripts/   All game code. Key files:
               GameData.gd   Character stats, the LEVEL TABLE,
                             monsters, difficulty, cheats, save
                             data and unlocks
               Level.gd      One script that builds and plays every
                             level from the level table, plus
                             Free Play
               Player.gd     The runner and jump input
               Obstacle.gd   Obstacles and bounce pads
               Art.gd, MonsterArt.gd, PixelRunner.gd
                             Art loading and drawn-in-code graphics
               Audio.gd      Music and sound effects
               Options.gd, Pause.gd, UIKit.gd, Credits.gd, etc.
  Sprites/   PNG art. See Sprites/README.txt for names and sizes.
             Missing files fall back to plain coloured boxes.
  Audio/     music_*.ogg and sfx_*.wav

Tweaking the game:

  * Change any level or character by editing the numbers at the top
    of Scripts/GameData.gd.
  * To add a level, copy one block in the "levels" list in
    GameData.gd and change the values. No new scene is needed.
  * Audio volume defaults (MUSIC_DB, SFX_DB) are at the top of
    Scripts/Audio.gd.
  * To replace a sound, drop a file with the same name into Audio/.
    Music comes in pairs (music_levelN.ogg and
    music_levelN_chase.ogg). Keep both the same length so they stay
    in sync.
  * To replace art, drop a PNG with the exact same name into Sprites/
    (facing right, transparent background).

Exporting: use Project > Export with the presets in
export_presets.cfg (Windows, Linux, macOS, Web).


---------------------------------------------------------------------
 CREDITS
---------------------------------------------------------------------

  Game:         MAXIMUS LARPUS

  Coding:       M. Safiullah, Zaid Ali Bajwa
  Designing:    Zaid Ali Bajwa, Zulkifal Khan
  Publishing:   Zaid Ali Bajwa

  Built with the Godot Engine (https://godotengine.org).

  Thanks for playing!

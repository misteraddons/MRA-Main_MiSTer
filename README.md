# Arcade-MRAs

## Purpose
The introduction of the MRA format and the creation of the Arcade Organizer script has made discovering and sorting arcade games much easier. I felt there is still room for improvement by standardizing the xml fields and curating a list of genres instead of using MAME's more than 200 game categories.

## Filename Schema
Name (1 or 2 letter region, version) [bl/hb].mra
### Examples:
```
Bubbles.mra	 
Donkey Kong (US, Set 2).mra
Zig Zag (Dig Dug Conversion, Set 2) [bl].mra
```
	
## Structure
This is the proposed MRA template
```
<misterromdescription>
	<name></name> (Main Title name without version or region, e.g. DoDonPachi)
	<region></region> (Country or region, e.g. USA, Japan, Europe, Germany, etc.)
	<homebrew></homebrew> (yes / no)
	<bootleg></bootleg> (yes / no)
	<version></version> (Set #, Rev #, etc.)
	<alternative></alternative> (Name of game this is an alternative of, e.g. DoDonPachi)
	<platform></platform> (Irem M62, Cave x68000, Sega System 1, etc.)
	<series></series> (Larger game series, e.g. DonPachi, Street Fighter, etc.)
	<year></year> (YYYY format)
	<manufacturer></manufacturer> (Try to format exactly as existing manufacturers, if they exist, to avoid duplicates)
	<manufacturer2></manufacturer2> (Optional)
	<manufacturer3></manufacturer3> (Optional)
	<category></category> (See list below)
	<category2></category2> (Optional)
	<category3></category3> (Optional)

	<setname></setname> (MAME rom name)
	<parent></parent> (MAME rom parent - may be the same as setname)
	<mameversion></mameversion> (Version of MAME ROM that mra is based on)
	<rbf></rbf> (Core name)
	<about></about> (About core or author)

	<resolution></resolution> (15kHz / 24kHz / 31kHz)
	<rotation></rotation> (horizontal / vertical (cw) / vertical (ccw))
	<flip></flip> (yes / no)

	<players></players> (1 / 2 (alternating) / 2 (simultaneous) 3 / 4)
	<joystick></joystick> (2-way horizontal, 2-way vertical, 4-way, 8-way)
	<special_controls></special_controls> (spinner, twin stick, trackball, etc).
	<num_buttons></num_buttons> (0 / 1 / 2 / 3 / 4 / 5 / 6)
	<buttons></buttons> (names="Attack, Jump, Start, Coin" default="A,B,Start,R")

	<switches></switches> (BIOS settings)

	<rom index="1"></rom>
	<rom index="0" md5="" zip=""></rom> (If no md5 is available, enter md5="none". Zip name is required.)
		<part crc="" name=""></part> (crc is required)
	<rom index="2"></rom> (Same as above, else leave empty)
	<rom index="3"></rom> (Same as above, else leave empty)
	<rom index="4"></rom> (Same as above, else leave empty)

	<nvram></nvram>

	<remark></remark> (Comments on the status or things to watch out for)

	<mratimestamp></mratimestamp> (yyyymmddhhmm)
</misterromdescription>
```

## Category
MAME has a massive list of game categories that are hilariously specific. I prefer a more concise list of categories based solely around gameplay mechanics.

Category | Description
-------- | -----------
Action | The catch-all category. Attempting to minimize the number of "Action" category games.
Arena | Usually an overhead, fixed screen, bounded game environment with X-Y movement (Robotron, Food Fight, Bull Fight, Bubbles, etc.)
Ball and Paddle | Everything from Pong to Arkanoid, Kick, Breakout, etc.
Beat 'em Up | Fight swarms of baddies moving along the x axis (and sometimes y-axis as well!)
Fighting | Street Fighter, etc.
Gambling | Slots, card games, etc.
Grid / Maze | Pac-Man style games where movement is restricted along a x-y grid
Lander | You're in a space ship and you need to touch down.
Mixed | Three Wonders, etc.
Platform - Climb | Up/down movement with platforms to jump up and down onto (Ninja-Kun, etc.)
Platform - Fixed | Single screen with platforms to jump up/down from (Solomon's Key, etc.)
Platform - Scroll| Left/right scrolling platformer (Wonder Boy, etc.)
Puzzle | Tetris, etc.
Puzzle - Platform | Bomb Jack, etc.
Quiz | Zzzzz
Racing | Start and finish lines
Run 'n' Gun - Horizontal | Contra, Metal Slug, etc.
Run 'n' Gun - Vertical | Commando, Mercs, etc.
Shooter - Gallery | Movement restricted to x-axis and typically enemies come in waves
Shooter - Horizontal | R-Type, Gradius, etc.
Shooter - Isometric | Zaxxon, etc.
Shooter - Multidirectional | Time Pilot, Vindicators, etc.
Shooter - Tube | Gyruss, etc.
Shooter - Vertical | 1942, etc.
Sports | Tennis, basketball, baseball, football, etc.

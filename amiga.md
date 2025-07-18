[Home](https://gotbasic.com) • [VB 7+](vb.md) • [VB 1-6](vb6.md) • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## AmigaBASIC

![Amiga](images/amiga_logo.svg.png)

AmigaBASIC is a BASIC language implementation for the earlier line of Amiga personal computers, designed and written by Microsoft. AmigaBASIC shipped with AmigaOS versions 1.1 to 1.3. It succeeded ABasiC, which was initially included in AmigaOS 1.0 (possibly even on some early 1.1 disks), and discontinued in AmigaOS version 2.0 onwards.

AmigaBASIC provided not only the common BASIC language, but also attempted to provide an easy-to-use API for the Amiga's unique graphics and sound capabilities. `OBJECT` commands, for example, made it easy to create moving objects - sprites and bobs that could be drawn with an external drawing program, Object editor, that was supplied with AmigaBASIC.

![Amiga BASIC](images/amiga_basic.png)

### Patch?

Although it is officially not supported (possible?) to run AmigaBASIC on newer AmigaOS versions... it does appear there is a [patch](http://aminet.net/package/dev/misc/PtchAmigaBASIC) that allows this. According to the notes related to the [patch](http://aminet.net/package/dev/misc/PtchAmigaBASIC)...

> There is one bad instruction in AmigaBASIC which the 68000 in a standard Amiga seems to execute properly.  A 68020 has trouble with this bad instruction and performs a Guru Meditation trap. This program will fix the bad instruction in AmigaBASIC.

Additionally, there also appears to be a tip written by Andreas Mixich (in an Amiga FAQ) about needing to...

- Run NoFastMem (or turn off FastMem).
- Switch off sound output in the Sound prefs editor.
- Better avoid SUBs and use GOSUBs instead, then the compatibility with newer processors will be higher.
There is a patch you should run at the beginning of AmigaBasic:

```vb
' AmigaBASIC patch to let AmigaBASIC work on A1200 and other newer machines.
' Start at the beginning of AmigaBASIC or invoke AmigaBASIC with this program
 
OPEN "AMIGABasic" AS 1 LEN=1
FIELD #1,1 AS d$
i&=&HF3*256+&H87 : PRINT i&
GET #1,i& : a$=HEX$(ASC(d$))
PRINT a$
IF a$="79" THEN
  LSET d$=CHR$(&H78)
  PUT #1,i&
END IF
CLOSE 1
```

Found elsewhere was this which was credited to a Dr. Peter Kittel...

**Can I run AmigaBasic on my A1200?**

To run AmigaBasic on the A1200 and A4000 you need to follow these steps:

- Disable sound output in the SoundPrefs editor in PREFS. This will prevent it from conflicting with the sound AmigaBasic produces.
- If you have fast ram, run the NoFastMem program in your System drawer.
- Avoid SUBs and use GOSUB instead to retain compatibility with higher processors.

### Utility: Convert to ASCII

To convert an AmigaBASIC binary formatted (tokenized) file to ASCII without using AmigaBASIC, check out [ab2ascii-1.3](http://aminet.net/package/dev/misc/ab2ascii-1.3).

### Books

- [Microsoft AmigaBASIC Manual](https://archive.org/details/AmigaBASIC1985Commodore/) ([Alternate](https://archive.org/details/AmigaBasic/))
- [Amiga 3D Graphic Programming in BASIC](https://archive.org/details/Amiga3dGraphicProgrammingInBasic/mode/2up): A revealing book on how to use the spectacular and powerful graphic capabilities of the Amiga.

### Samples

- [Rosetta Code](https://rosettacode.org/wiki/Category:AmigaBASIC)

### Blogs

- [Beginners Guide to Amiga Basic](https://blog.mikaellundin.name/2016/02/03/beginners-guide-to-amiga-basic.html)
- [Hardware Access using AmigaBASIC](https://web.archive.org/web/20101224192910/http://thecryptmag.com/Online/53/hardwareaccess.htm)

### Articles

- COMPUTE!
  - The Beginner's Page
    - [#20 - Loops](https://www.atarimagazines.com/compute/issue20/128_1_The_Beginners_Page.php)
    - [#21 - Translating Equations](https://www.atarimagazines.com/compute/issue21/Translating_Equations.php)
    - [#23 - Making Decisions](https://www.atarimagazines.com/compute/issue23/007_1_The_Beginners_Page.php)
    - [#29 - Writing Your First Game](https://www.atarimagazines.com/compute/issue29/BEGINNERS_PAGE_WRITING_YOUR_FIRST_GAME.php)
    - [#30 - Arrays](https://www.atarimagazines.com/compute/issue30/BEGINNERS_PAGE_ARRAYS.php)
    - [#32 - Myths About Programming](https://www.atarimagazines.com/compute/issue32/020_1_THE_BEGINNERS_PAGE.php)
    - [#38 - Writing a Simulation Game](https://www.atarimagazines.com/compute/issue38/007_1_THE_BEGINNERS_PAGE.php)
    - [#40 - Machine Minds](https://www.atarimagazines.com/compute/issue40/machine_minds.php)
    - [#41 - Your First Useful Program](https://www.atarimagazines.com/compute/issue41/YOUR_FIRST_USEFUL_PROGRAM.php)
    - #42 - Zones Of Unpredictability - Part 1
    - [#43 - Zones Of Unpredictability - Part 2](https://www.atarimagazines.com/compute/issue43/139_1_THE_BEGINNERS_PAGE.php)
    - [#46 - Computer Amnesia](https://www.atarimagazines.com/compute/issue46/048_1_THE_BEGINNERS_PAGE.php)
    - [#47 - Size, Speed or Clarity](https://www.atarimagazines.com/compute/issue47/107_1_THE_BEGINNERS_PAGE.php)
    - [#48 - A Random Leap](https://www.atarimagazines.com/compute/issue48/beginners_page.php)
    - [#49 - A Wall Of Loops](https://www.atarimagazines.com/compute/issue49/395_1_THE_BEGINNERS_PAGE.php)
    - [#50 - Trapping Bugs](https://www.atarimagazines.com/compute/issue50/256_1_THE_BEGINNERS_PAGE.php)
    - [#53 - Logical Dreams](https://www.atarimagazines.com/compute/issue53/045_1_THE_BEGINNERS_PAGE.php)
    - [#55 - Learning To Program](https://www.atarimagazines.com/compute/issue55/beginner.php)
    - [#56 - Which Computer Language Is Best?](https://www.atarimagazines.com/compute/issue56/130_1_THE_BEGINNERS_PAGE.php)
    - [#57 - IF-THEN Intelligence](https://www.atarimagazines.com/compute/issue57/beginners_page.html)
    - [#58 - Two Kinds Of Logic](https://www.atarimagazines.com/compute/issue58/beginners_page.html)
    - [#59 - Programs Within Programs](https://www.atarimagazines.com/compute/issue59/beginners_page.php)
    - [#60 - Assembly Line Computing](https://www.atarimagazines.com/compute/issue60/189_1_THE_BEGINNERS_PAGE.php)
    - [#61 - FOR-NEXT Applications](https://www.atarimagazines.com/compute/issue61/318_1_THE_BEGINNERS_PAGE.php)
    - [#64 - Forget Your Algebra](https://www.atarimagazines.com/compute/issue64/beginners_page.php)
    - [#65 - Clearing Up Variable Cloudiness](https://www.atarimagazines.com/compute/issue65/beginners_page.php)
    - [#67 - No Strings Attached](https://www.atarimagazines.com/compute/issue67/353_1_The_Beginners_Page.php)
    - [#70 - Cutting Strings Without Scissors](https://www.atarimagazines.com/compute/issue70/115_1_The_Beginners_Page.php)
    - [#71 - More String-Slicing](https://www.atarimagazines.com/compute/issue71/beginners.php)
    - [#72 - String Comparisons](https://www.atarimagazines.com/compute/issue72/beginners_page.php)
    - [#73 - More String Arithmetic](https://www.atarimagazines.com/compute/issue73/beginners_page.php)
    - [#74 - Turning Apples Into Oranges](https://www.atarimagazines.com/compute/issue74/the_beginners_page.php)
    - [#75 - Advanced String Features](https://www.atarimagazines.com/compute/issue75/The_Beginners_Page.html)
    - [#77 - The Many Faces of PRINT](https://www.atarimagazines.com/compute/issue77/beginners_page.php)
    - [#78 - More About PRINTing](https://www.atarimagazines.com/compute/issue78/044_1_The_Beginners_Page.php)
    - [#79 - Arrays](https://www.atarimagazines.com/compute/issue79/The_Beginners_Page.php)
    - [#80 - DATA Statements](https://www.atarimagazines.com/compute/issue80/the_beginners_page_data_statements.php)
    - [#86 - Using Variables](https://www.atarimagazines.com/compute/issue86/031_1_The_Beginners_Page.php)
    - [#87 - Program Loops](https://www.atarimagazines.com/compute/issue87/The_Beginners_Page.php)
    - [#88 - Interactive Programming](https://www.atarimagazines.com/compute/issue88/The_Beginners_Page.php)
    - [#89 - Detecting Keypresses](https://www.atarimagazines.com/compute/issue89/The_Beginners_Page.php)
    - [#90 - The Random Function](https://www.atarimagazines.com/compute/issue90/The_Beginners_Page.php)
    - [#92 - Drawing Lines](https://www.atarimagazines.com/compute/issue92/271_1_The_Beginners_Page.php)
    - [#94 - Making Music With BASIC](https://www.atarimagazines.com/compute/issue94/P55_1_THE_BEGINNERS_PAGE_MAKING_MUSIC_WITH_BASIC.php)
    - [#95](https://www.atarimagazines.com/compute/issue95/053_1_THE_BEGINNERS_PAGE_USING_DISKS.php)
  - The Elementary Amiga  
    - Part 1 #91
    - [Part 2 #92](https://www.atarimagazines.com/compute/issue92/285_1_The_Elementary_Amiga.php)
    - Part 3 #93
    - [Part 4 #94](https://www.atarimagazines.com/compute/issue94/P69_1_THE_ELEMENTARY_AMIGA.php)
    - [Part 5 #95](https://www.atarimagazines.com/compute/issue95/060_1_THE_ELEMENTARY_AMIGA.php)
  - [Writing Transportable BASIC - Part 1 #32](https://www.atarimagazines.com/compute/issue32/015_1_PART_I_WRITING_TRANSPORTABLE_BASIC.php)
  - [Requester Windows In Amiga BASIC #70](https://www.atarimagazines.com/compute/issue70/106_1_Requester_Windows_In_Amiga_BASIC.php)
  - [Switchbox #70](https://www.atarimagazines.com/compute/issue70/061_1_Switchbox.php)
  - [Tug-A-War #71](https://www.atarimagazines.com/compute/issue71/tug_a_war.php)
  - [Amiga Puzzle #72](https://www.atarimagazines.com/compute/issue72/amiga_puzzle.php)
  - [UFO Invasion For IBM And Amiga #73](https://www.atarimagazines.com/compute/issue73/ufo_invasion.php)
  - [Meet ED The AmigaDOS Editor #73](https://www.atarimagazines.com/compute/issue73/amigados_editor.php)
  - [Getting Down to BASICs #74](https://www.atarimagazines.com/compute/issue74/getting_down_to_basics.php)
  - [Readers Feedback #74](https://www.atarimagazines.com/compute/issue74/readers_feedback.php)
  - [Hex War #74](https://www.atarimagazines.com/compute/issue74/hex_war.php)
  - [Foolproof Input For Amiga BASIC #75](https://www.atarimagazines.com/compute/issue75/Foolproof_Input_For_Amiga_BASIC.html)
  - [Tightrope #75](https://www.atarimagazines.com/compute/issue75/Tightrope.html)
  - [Amiga BASIC Style #76](https://www.atarimagazines.com/compute/issue76/AmigaBASIC.php)
  - [Be Hive #76](https://www.atarimagazines.com/compute/issue76/Beehive.php)
  - [Reader Feedback #76](https://www.atarimagazines.com/compute/issue76/Feedback_9.php)
  - [Pyramid Power For The Amiga](https://www.atarimagazines.com/compute/issue77/Pyramid_Power_For_The_Amiga.php)
  - [Amiga Math Graphics #77](https://www.atarimagazines.com/compute/issue77/Amiga_Math_Graphics.php)
  - [Biker Dave #78](https://www.atarimagazines.com/compute/issue78/018_1_Biker_Dave.php)
  - [Reader Feedback #79](https://www.atarimagazines.com/compute/issue79/Readers_Feedback5.php)
  - [Laser Strike #79](https://www.atarimagazines.com/compute/issue79/Laser_Strike.php)
  - [The Great Graphics Leap #80](https://www.atarimagazines.com/compute/issue80/the_great_graphics_leap.php)
  - [Chain Reaction #80](https://www.atarimagazines.com/compute/issue80/chain_reaction.php)
  - [Zookeeper For The Amiga #86](https://www.atarimagazines.com/compute/issue86/046_1_Zookeeper_For_The_Amiga.php)
  - [Weather Wizard #86](https://www.atarimagazines.com/compute/issue86/022_1_Weather_Wizard.php)
  - [Fractal Mountains For Amiga #87](https://www.atarimagazines.com/compute/issue87/Fractal_Mountains_For_Amiga.php)
  - [Climber 5 #87](https://www.atarimagazines.com/compute/issue87/Climber_5.php)
  - [Amiga SuperMenus #88](https://www.atarimagazines.com/compute/issue88/Amiga_SuperMenus.php)
  - [Amiga And 64 RAMdisk Files #88](https://www.atarimagazines.com/compute/issue88/Amiga_And_64_Ramdisk_Files.php)
  - [Monte Carlo #88](https://www.atarimagazines.com/compute/issue88/Monte_Carlo.php) 
  - [A BUTTON Command #89](https://www.atarimagazines.com/compute/issue89/Button_Command.php)
  - [Word War #89](https://www.atarimagazines.com/compute/issue89/Word_War.php)
  - [Marbles #89](https://www.atarimagazines.com/compute/issue89/Marbles.php)
  - [IFF To Icon Translator](https://www.atarimagazines.com/compute/issue90/IFF_To_Icon_Translator.php)
  - [Masked Input For The Amiga #90](https://www.atarimagazines.com/compute/issue90/Masked_Input_For_The_Amiga.php)
  - [The Fastest Amiga Language #90](https://www.atarimagazines.com/compute/issue90/Feedback_Fastest_Amiga.php)
  - [The Hermit #90](https://www.atarimagazines.com/compute/issue90/The-Hermit.php)
  - [CAPUTE! #90](https://www.atarimagazines.com/compute/issue90/Capute.php)
  - [Canfield #92](https://www.atarimagazines.com/compute/issue92/262_1_Canfield.php)
  - [Casino Blackjack #94](https://www.atarimagazines.com/compute/issue94/P30_1_CASINO_BLACKJACK.php)
  - [Graphics And Music In Amiga Basic #95](https://www.atarimagazines.com/compute/issue95/043_2_READERS_FEEDBACK_GRAPHICS_AND_MUSIC_IN_AMIGA_BASIC.php)
  - [The Pyramid Game #95](https://www.atarimagazines.com/compute/issue95/P70_1_THE_PYRAMID_GAME.php)
  - [AMIGA #117](https://www.atarimagazines.com/compute/issue117/p16_specific4_AMIGA.php)

### Videos

- [Coding Christmas Like It's 1985 - Amiga BASIC Nostalgia](https://youtu.be/5LIPBsuW89M)
- [Utilizing Amiga System Libraries in Amiga BASIC](https://youtu.be/gA63GTN_knY)
- [Avoiding library function name conflicts in Amiga BASIC](https://youtu.be/1P3j44hE9wk)
- [Amiga Basic Graphics](https://youtu.be/DVDbH-M6IA0)
- [Microsoft Amiga BASIC (Workbench 1.3)](https://youtu.be/fsOO5wIGl70)

Additional videos that are not BASIC specific, but could be helpful.

- [Remembering how to using AmigaDOS (because it's been like 30 years)](https://youtu.be/x4jZXKJct9M)

### Alternative: ABasiC

- [MetaComCo ABasiC](https://archive.org/details/Amiga_BASIC_v1.0_1985_Commodore_Microsoft): Note that the entry is mislabeled, but a commenter pointed out which version of BASIC this actually is. See [MetaComCo](https://en.wikipedia.org/wiki/MetaComCo).
- [Patch Metacomco's ABasiC to work on OS2+](http://aminet.net/package/dev/basic/ABasiC_patch)
- [Collection of ABasiC games and programs](http://aminet.net/package/dev/basic/ABasiC_progs)

### Alternative: ACE

ACE is a freeware AmigaBASIC compiler which produces 68000 assembly source code. ACE runs under all versions of the operating system from Release 1.3, as do the executables it produces.

ACE supports a large subset of AmigaBASIC. It also provides a variety of commands, functions and features not found in AmigaBASIC.

### Alternative: AMIBLITZ³

- [AMIBLITZ³](blitz.md): AMIBLITZ³ is a free Development environment for AmigaOS3.x and Compatible based on BlitzBasic.
- [How to install Amiblitz / Blitz Basic 3 on the Commodore Amiga running on WinUAW](https://youtu.be/BftEFLlSWhI)

### Alternative: AQB

- [AQB](https://github.com/gooofy/aqb): A QuickBASIC-style Compiler and IDE for Amiga computers.

### Alternative: Cursor

[Cursor](http://aminet.net/package/dev/basic/Cursor) is a free compiler available for AmigaBASIC. It also includes a simple editor which can control the compiler. Runs  with Kickstart 1.2 or later with 512K RAM. Get it [here](http://aminet.net/package/dev/basic/Cursor).

### Alternative: GFA BASIC

TBD

### Alternative: HiSoft BASIC 

TBD

### Alternative: PureBasic 4.00

TBD

### More

- [WHDLoad: Workbench 1.3](https://www.whdload.de/apps/Workbench13.html)
- [The Hacking Way: Part 1 - First Steps](https://wiki.amigaos.net/wiki/The_Hacking_Way:_Part_1_-_First_Steps)

### Hardware Emulation (FPGA)

![Amiga 500](images/amiga500.jpg)

- [Amiga on MiSTer](https://www.mistercores.com/amiga-core/)

## Additional

- [BitmapFonts](https://github.com/ianhan/BitmapFonts): Collection of bitmap fonts pulled from various demoscene archives over the years.


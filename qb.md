[Home](https://gotbasic.com) • [VB 7+](vb.md) • [VB 1-6](vb6.md) • [FB](freebasic.md) • [QB64](qb64.md) • QB45 • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

# Microsoft QuickBASIC, PDS BASIC and QBasic

## Where can you find a download?

- If you have a copy of Windows XP; look for the olddos.exe file which contains QBasic 1.1.
- [QBasic](http://members.optusnet.com.au/mskeon/qbastest.html)([Additional Details.](https://answers.microsoft.com/en-us/windows/forum/windows_7-windows_programs/the-case-for-quick-basic-in-the-21st-century/dbc79c0a-9f4a-4e32-824f-7a0672628ccd?auth=1))
- See alternative [QB64](QB64.md)...
- See alternative [FreeBASIC](FreeBASIC.md)...
- See alternative [Bsharp (B#)](https://github.com/DualBrain/bsharp)...
- See alternative [QBC](QBC.md)...

## Online?

- [CLASSIC RELOAD - QuickBASIC](https://classicreload.com/dosx-quickbasic.html)
- [QBasic Online Compiler](https://codedamn.com/online-compiler/qbasic)

## Tutorials

- [QBasic for Beginners](https://www.qbasic.net/en/qbasic-tutorials/beginner/qbasic-beginner-1.htm)
- [QBASIC Programming for Kids by Ted Felix](http://tedfelix.com/qbasic/)

## Third-Party Extensions

The following products from the company formally known as *Crescent Software* and *Full Moon Software* have all been generously made [freely available (meaning **public domain**)](http://annex.retroarchive.org/crescent/index.html) (with source) via GitHub (linked below).  You can also find more details on this directly from the original author (and, dare I say, legend) [Ethan Winer](http://ethanwiner.com/fullmoon.html).

- [QuickPak Professional for DOS (Crescent Software)](https://github.com/geneb/QuickPak-Pro-DOS): The most comprehensive collection of BASIC tools ever produced.
- [P.D.Q. (Crescent Software)](https://github.com/geneb/PDQ): A revolutionary concept in high-level languages.
- [QB Plus (Crescent Software)](https://github.com/geneb/QBPlus): A collection of software accessories developted for the QuickBASIC programmer.
- [Don Malin's XREF (Crescent Software)](https://github.com/geneb/XREF): The most sophisticated cross-reference program ever developed.
- [QuickScreen (Crescent Software)](https://github.com/geneb/QuickScreen): Tools to create text entry screens in QuickBASIC 4.x and PDS 7.x.
- [QuickPak Scientific (Crescent Software)](https://github.com/geneb/QuickPakScientific): A powerful numerical analysis toolbox for DOS compiled BASIC.
- [QuickMenu (Crescent Software)](https://github.com/geneb/QuickMenu): A DOS menuing system.
- [PDQComm (Crescent Software)](https://github.com/geneb/PDQComm): Add full-featured communications to your compiled BASIC programs.
- [LaserPak (Crescent Software](https://github.com/geneb/LaserPak): A comprehensive set of subroutines for generating graphics on a laserjet or compatible.
- [GraphPak Professional (Crescent Software)](https://github.com/geneb/GraphPak): Add professional-looking graphs and charts to your programs.
- [The Graphics Workshop (Crescent Software)](https://github.com/geneb/GraphicsWorkshop): Create blazing fast graphics with half the code.
- [Graphics QuickScreen (Crescent Software)](https://github.com/geneb/Graphics-QuickScreen): Tools to create graphics entry screens in QuickBASIC 4.x, PDS 7.x and VBDOS.
- [Compression Workshop (Crescent Software)](https://github.com/geneb/CompressionWorkshop): Routines to compress and decompress data.
- [QBase](https://github.com/geneb/QBase): Database system.

There are many, many, many others that provided third-party tools...

- [Fastgraph for DOS](http://fastgraph.com/catalog.html): Assembly language graphics powerhouse providing not only raw speed but ease of doing so. This is an amazing product the deserves a solid mention for the DOS BASIC developer. Will also mention when combined with [Fastgraph/Fonts](http://fastgraph.com/catalog.html) and [Fastgraph/Image](http://fastgraph.com/catalog.html) you could pretty much accomplish anything in BASIC that could be done in any language available for DOS.

## Resources

- [QB45.org](https://qb45.org/): About programming in QBasic/QuickBASIC, the programming language that was developed by Microsoft.
- [QBasic Source Code Public Domain](https://thedubber.altervista.org/qbsrc.htm)

## Communities

- [QuickBASIC Cafe](https://www.qbasic.net/)
- [Pete's QBASIC / QuickBasic Site](www.petesqbsite.com/)

## Interesting Projects

- [A Markdown implementation for FreeDOS](https://github.com/clasqm/QBASDOWN): Convert (parse) markdown (.md) files into HTML.
- [GUI Reviews](http://qbasicgui.datacomponents.net/)

## GW-BASIC to QBasic

### Summary

To run a GW-Basic program under QBasic, do the following:  

1. Convert the program in GW-Basic to ASCII format.  
2. Run QBasic with the /MBF switch.  
3. Load the program into QBasic.  

### Details

All QBasic programs must be in ASCII format. The GW-Basic program editor can save programs in the format QBasic requires. The file must be saved with the A option in GW-Basic. Otherwise, GW-Basic compresses the text of your program into a format that QBasic cannot read.  

To convert the file to the QBasic format, do the following:  

1. Run GW-Basic.  
2. Use the LOAD command to load your GW-Basic program.  
3. Use the LIST command to verify your program's contents.  
4. Use the SAVE command with the A option to save the program. The A switch causes the program to be saved in ASCII format. For example:  

save"<program name>",a  
  
5. Exit GW-Basic by typing SYSTEM at the GW-Basic prompt.  

Once you have saved the program in ASCII format, you can then load the program in QBasic using the /MBF switch. MBF stands for Microsoft Binary Format, which is used for floating point numbers and calculations. It allows you to use your old programs and data without rewriting your programs or changing your files. For example, type the following command and press ENTER:  

qbasic /mbf  

You can determine if your program is in ASCII format by loading the program into QBasic. If it has strange characters or IBM extended character set characters, the program is probably not in ASCII format. End your QBasic session and save the file in ASCII format using the steps above.  

To run the program in QBasic, from the Run menu, choose Start. If the program is converted to ASCII, it should run normally.  

## Libraries

QuickPak Professional is a programmer's toolbox of more than 500 BASIC and assembly language subroutines, designed to help developers improve the quality of their programs and complete them faster. Included are routines for windowing, access to DOS and BIOS services, searching and sorting any type of BASIC array, creating pull-down and Lotus(r) style menus, accepting data input, and much more. Extensive documentation (700 pages) is provided with additional tutorials on files, arrays, subprograms, sorting, compiling and linking, plus many other related topics. The manual is clearly written, and includes a wealth of information useful and pertinent for programmers at all levels of experience. We provide pre-built Quick and linking libraries for use with all current versions of Microsoft BASIC for DOS--simply load the appropriate library, and you're ready to go. The high-level routines written in BASIC are easily loaded as source modules.

Thanks to Gene Buckle for purchasing and releasing all of Full Moon Software's (aka Crescent Software's) tools to the public domain.

- [All Full Moon Software (aka Crescent Software) Tools](http://annex.retroarchive.org/crescent/index.html)
- [QuickPak Professional for DOS on GitHub](https://github.com/geneb/QuickPak-Pro-DOS)

## SUPER COOL PROJECTS!

- [The M.I.C.E. Project - The (World's) Most Ill-Concieved Emulator: A TRS-80 Model I Emulator in GW-BASIC.](http://www.vavasour.ca/jeff/mice.html)
- [RogCAD 3D design software - mz-.bas data-file reader](https://rogcad.com/mzbas.htm)

## Resources

- [Q41581: More Information about BASIC's DRAW Statement Macro Language](https://jeffpar.github.io/kbarchive/kb/041/Q41581/)
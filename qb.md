[Home](https://gotbasic.com) • [VB 7+](vb.md) • [VB 1-6](vb6.md) • [FB](freebasic.md) • [QB64](qb64.md) • QB45 • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

# Microsoft QuickBASIC, PDS BASIC and QBasic

## Where can you find a download?

- If you have a copy of Windows XP; look for the olddos.exe file which contains QBasic 1.1.
- [QBasic](http://members.optusnet.com.au/mskeon/qbastest.html)([Additional Details.](https://answers.microsoft.com/en-us/windows/forum/windows_7-windows_programs/the-case-for-quick-basic-in-the-21st-century/dbc79c0a-9f4a-4e32-824f-7a0672628ccd?auth=1))
- See alternative [QB64](QB64.md)...
- See alternative [FreeBASIC](FreeBASIC.md)...

## Tutorials

- [QBasic for Beginners](https://www.qbasic.net/en/qbasic-tutorials/beginner/qbasic-beginner-1.htm)

## Communities

- [QuickBASIC Cafe](https://www.qbasic.net/)
- [Pete's QBASIC / QuickBasic Site](www.petesqbsite.com/)

## Interesting Projects

- [A Markdown implementation for FreeDOS](https://github.com/clasqm/QBASDOWN): Convert (parse) markdown (.md) files into HTML.

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

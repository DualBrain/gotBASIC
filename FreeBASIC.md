# FreeBASIC

FreeBASIC is a completely free, open-source, multi-platform BASIC compiler, with syntax similar to MS-QuickBASIC, that adds new features such as pointers, unsigned data types, inline assembly, object orientation, and many others.

- [FreeBASIC](https://www.freebasic.net/)
- [FreeBASIC (GitHub)](https://github.com/freebasic/fbc)
- Xuisinboy Bekchanov
  - [VisualFBEditor - IDE (GitHub)](https://github.com/XusinboyBekchanov/VisualFBEditor)
  - [MyFbFramework - My FreeBasic Framework (GitHub)](https://github.com/XusinboyBekchanov/MyFbFramework)
- Paul Squires
  - [FreeBASIC Editor for Windows (GitHub)](https://github.com/PaulSquires/WinFBE)
  - [Windows Form Library (GitHub)](https://github.com/PaulSquires/WinFormsX)
- Jose Roca
  - [Windows Framework (GitHub)](https://github.com/JoseRoca/WinFBX)
- [FbFrog (GitHub)](https://github.com/dkl/fbfrog): FreeBASIC binding creation tool.
- [FbFrog Scripts (GitHub)](https://github.com/dkl/fbbindings): Scripts for fbfrog-based FreeBASIC bindings.
- [FbRtLib (Github)](https://github.com/ImortisInglorian/fbrtLib): FreeBASIC Runtime Library written in FreeBASIC.
- [Batched Files](https://github.com/BatchedFiles)
  -[Station992 - Http Server (GitHub)](https://github.com/BatchedFiles/Station922)
  -[Client library for IRC (GitHub)](https://github.com/BatchedFiles/IrcClientLibrary)
- ["Nine" Card Game (GitHub)](https://github.com/TagalongGames/Nine)
- [FreeBASIC in Russian (Unofficial)](http://www.freebasic.su/)

## FreeBASIC vs GW-BASIC 

By default, FreeBASIC doesn't have support for line number and other "deprecated" language features.  However, if you specify the -lang commandline parameter, these features are enabled.  Some other areas of note (these need to be verified):

- KEY ON / OFF is not supported as FreeBASIC is more compatible with QB than GW-BASIC; which also did not have KEY ON / OFF.  However, QB would just ignore the command; FreeBASIC requires that you modify the code.
- KEY (#) ON/OFF and ON KEY (#) GOSUB is not supported.  Again, somewhat expected.  The closest you can mimic the behavior is through the INKEY$ and utilize polling.
- DEF FNname() not supported.  Since you can create actual functions this, again, is somewhat to be expected.
- EXTERR() not supported.
- GOSUB # ... RETURN doesnt work unless you specify "-lang qb".  The line number support can be enabled with "-lang deprecated".  Yet if you try to call RETURN it reports "Illegal outside blah blah blah or SUB block".
- SCREEN() isn't supported.  Not the SCREEN() command, the SCREEN() function.

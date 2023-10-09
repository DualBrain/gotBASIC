[Home](https://gotbasic.com) • [VB 7+](vb.md) • [VB 1-6](vb6.md) • FB • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

# FreeBASIC

FreeBASIC is a completely free, open-source, multi-platform BASIC compiler, with syntax similar to Microsoft QuickBASIC, that adds new features such as pointers, unsigned data types, in-line assembly, object orientation, and many others. Although certainly began as a project that focused on compatibility with QB; it has since evolved into its having its own individual identity. It's certainly one of the modern BASIC's to have in your personal toolbelt!

From what I understand, the developer primarily responsible for FreeBASIC is [JayRM](https://github.com/jayrm).

## Official Website

- [FreeBASIC](https://www.freebasic.net/)

## Official Discord Server

- [FreeBASIC (Discord)](https://discord.com/invite/286rSdK)

## Official Project

- [FreeBASIC (GitHub)](https://github.com/freebasic/fbc)
- [FbFrog (GitHub)](https://github.com/freebasic/fbfrog/): FreeBASIC binding creation tool.
- [FbFrog Scripts (GitHub)](https://github.com/freebasic/fbbindings): Scripts for fbfrog-based FreeBASIC bindings.

## IDE

- FBIde
  - [FBIde](https://fbide.freebasic.net/): The "#1 editor for FreeBASIC".
- Xuisinboy Bekchanov
  - [VisualFBEditor - IDE (GitHub)](https://github.com/XusinboyBekchanov/VisualFBEditor)
- Paul Squires
  - [FreeBASIC Editor for Windows (GitHub)](https://github.com/PaulSquires/WinFBE)
- Kuan Hsu
  - [PoseidonFB](https://bitbucket.org/KuanHsu/poseidonfb): [Forum discussion](https://www.freebasic.net/forum/viewtopic.php?t=23935)

## Libraries

- Xuisinboy Bekchanov
  - [MyFbFramework - My FreeBasic Framework (GitHub)](https://github.com/XusinboyBekchanov/MyFbFramework)
- Paul Squires
  - [Windows Form Library (GitHub)](https://github.com/PaulSquires/WinFormsX)
- [Batched Files](https://github.com/BatchedFiles)
  - [Station992 - Http Server (GitHub)](https://github.com/BatchedFiles/Station922)
  - [Client library for IRC (GitHub)](https://github.com/BatchedFiles/IrcClientLibrary)

## Additional Resources

- Luther Ramsey
  - [FbRtLib (Github)](https://github.com/ImortisInglorian/fbrtLib): FreeBASIC Runtime Library written in FreeBASIC.
- Jose Roca
  - [Windows Framework (GitHub)](https://github.com/JoseRoca/WinFBX)
- JayRM
  - [JayRM's FreeBASIC Load Out](https://github.com/jayrm/fblo): Prebuilt libraries for Win32/Win64 and source files that can be dropped in to an existing FreeBASIC install.
- Others
  - ["Nine" Card Game (GitHub)](https://github.com/TagalongGames/Nine)
  - [FreeBASIC in Russian (Unofficial)](http://www.freebasic.su/)
  - [Compiling FB for DOS](https://www.freebasic.net/wiki/DevBuildDos)

## FreeBASIC vs GW-BASIC 

By default, FreeBASIC doesn't have support for line number and other "deprecated" language features.  However, if you specify the `-lang` command-line parameter, these features are enabled.  Some other areas of note (these need to be verified):

- `KEY ON / OFF` is not supported as FreeBASIC is more compatible with QB than GW-BASIC; which also did not have KEY `ON` / `OFF`.  However, QB would just ignore the command; FreeBASIC requires that you modify the code.
- `KEY (#) ON/OFF` and `ON KEY (#) GOSUB` is not supported.  Again, somewhat expected.  The closest you can mimic the behavior is through the `INKEY$` and utilize polling.
- `DEF FNname()` not supported.  Since you can create actual functions this, again, is somewhat to be expected.
- `EXTERR()` not supported.
- `GOSUB # ... RETURN` doesn't work unless you specify "`-lang qb`".  The line number support can be enabled with "`-lang deprecated`".  However, even when enabled, there are still some restrictions on it's use when compared to QB.
- `SCREEN()` isn't supported.  Not the `SCREEN()` command, the `SCREEN()` function.

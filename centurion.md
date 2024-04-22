[Home](https://gotbasic.com) • [VB 7+](vb.md) • [VB 1-6](vb6.md) • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

# Centurion BASIC

![Centurion](images/centurion.png)

The Centurion mini-computer is a bit of a (almost) forgotten relic if not for the efforts of [Usagi Electric (YouTube)](https://www.youtube.com/playlist?list=PLnw98JPyObn0wJFdbcRDP7LMz8Aw2T97V). In addition to his videos, he has an awesome set of documentation available at [CenturionComputer (GitHub)](https://github.com/Nakazoto/CenturionComputer) covering history, time-line, hardware and software. Additionally, there are active members of the growing retro Centurion community creating new content around this platform; many of them hang out over on the [Usagi Electric (Discord)](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkFOam55OGhyYmNCdHY5eWFGb0tYb2VySUZQUXxBQ3Jtc0tuNDUtQjNVTnJSNFVWTXF4c1NMNFFsNndjQUJNcXpVWUU3TTVZYm9uNmhvdE1UVUtYaVMxNU4wNkIwblhDck80Nm1SbnFZT0kzRHdGeGE1aEFtUDkwWlZIN3RmdS16bllnNlZmYVZKYmR4WHltbElvdw&q=https%3A%2F%2Fdiscord.gg%2Fp7UsfHD&v=0k3Mb6SSLAk) server.

With a bit of that background out of the way, let's zero in on the BASIC available on this platform. Unfortunately, at least as of the time of this writing, there doesn't appear to be any available (historical) documentation on this (what appears to be a) custom dialect; however, the community has taken the time to reverse engineer the binary so we do have [*some* documentation (GitHub)](https://github.com/Nakazoto/CenturionComputer/wiki/BASIC-(Basic-Programming-Language)) that can be utilized to better experiment. This is great, but I hear what you are thinking... "we don't have a machine!". This is where [Meisaka's Web Based Emulator (GitHub)](https://github.com/Nakazoto/CenturionComputer/wiki/Meisaka's-Web-Based-Emulator) comes in allowing us to access the "machine" thanks to emulation. The web-based emulator can be found [here](https://eciv.net/meisaka/cen/cen.html).

> This is where things get a bit tricky as the copyright holders of the Centurion appear to remain in the "frowning upon" stage of the OS being redistributed - hopefully this will change. Assuming you have access to a working system, we can continue on our journey.

Now I'll be honest here, the emulator certainly seems overwhelming with all of the various *windows* that are displayed by default. So my first step I took to *reduce the noise* was click on `Settings` and disabled several of the panels/windows as well as modified `CRT0` to be 3x size.

With that out of the way, needed to get the machine to boot... to do so, followed these steps:

- Drag/drop the disk image from my local file system to the browser window. Doing so reflects that it is loaded under the `DSKII/EMU` panel.
- Click the `R/F` to turn it on.
- Click `OpSys` to turn `S2` on.
- Click `100k` (at the very top).
- Click `RUN/STOP` to, well, run.
- At this point `CRT0` should display the `D=` prompt, type `H1` to initiate loading the OS.
- When loaded completes, it displays `MAX DISK = 1. SYSTEM DISK = 1` and will wait for your input. Press `Enter`.
- Work through the date and time prompts.
- Now should be at the point where `CRT0 READY` is displayed. To verify all is good, enter the command `.STA` to execute the status output.

> Many thanks to *Usagi Electric*; credit goes to him for the above above instructions.

At this point the OS is loaded and we can now work with BASIC!

It's important to keep in mind that this is from *an earlier time*... one before the age of the "interpreter" BASIC most of us are familiar with on home computers. So in order to write BASIC programs on the Centurion, you have to follow the general work flow of:

- create a text file.
- write your code to this text file.
- "compile" your code.
- execute your "compiled" result.

It is important to note that on the Centurion, the BASIC "compiler" doesn't create native binaries - it will instead create a sort of byte code that will then need to execute within the "BASIC MONITOR" which has to be loaded into memory before attempting to execute your compiled program.

The Centurion also doesn't appear to have a dedicated BASIC editor, so you have to use the *Kompoz* editor or, thanks to the community, the "modern" editor for Centurion apply named [CED (GitHub)](https://github.com/Nakazoto/CenturionComputer/wiki/CED).

There are more details on the edit/compile/execute process [located here](https://github.com/Nakazoto/CenturionComputer/wiki/BASIC-(Basic-Programming-Language)).

> I'm planning on exploring this dialect further as there are certainly several *unique* things about it that peak my interest.

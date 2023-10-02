[Home](https://gotbasic.com) • [VB 7+](vb.md) • [VB 1-6](vb6.md) • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Microsoft Small Basic

According to the [official website](http://smallbasic.com):

*"Small Basic is the **only** programming language created specially to help students transition from block-based coding to text-based coding. By teaching the fundamental elements of syntax-based languages in an approachable manner, Small Basic gives students the skills and confidence to tackle more complex programming languages such as Java and C#. You can also build applications for Kinect, Lego Mindstorm, Raspberry Pi, Arduino, Oculus Rift, and more using Small Basic.*

*From age 7 to 107, Small Basic is one of the easiest ways to learn to code."*

**BEGIN RANT!!**

*Really?!?!*

I'm planning on doing a full video and write up on this product.  Fair warning, this isn't going to be very pretty!  

Although I applaud the effort, it's pretty clear to me that the people (or person) that originally designed the language is not someone whom is familiar with BASIC.  

What follows is not an exhaustive list of "issues" I see, but I believe this gives a bit of a window into why I am so disappointed:  

- Application has no automatic update or even any sort of indication that there is a new version available.
- In order to upgrade you have to uninstall/reinstall.
- Methods require that you have parens around the parameters.
- Appears to support the concept of subroutines; however, no ability to pass parameters (so what is the point).  This basically hamstrings the ability to create reusable code or have code that easily be shared/reused. All in an environment that encourages sharing of code.
- Sort of related to the previous entry, all variables are global in scope.
- Arrays don't have square brackets.
- Because TextWindow.WriteLine("Hello World") is SOOOO much better than PRINT "Hello World". ;-)
- Start here so you can move to Java and C#????? What about VB?
- There is the whole "graduate" thing that doesn't work.
- On the official blog (at the time of making this list), the first entry is an [example](http://smallbasic.com/program/?NHT122-2).  Going to this example in Internet Explorer you'll find that there is a Silverlight version of the "compiler".  Running the application... it doesn't work.  OK, let's check to see if it works in the Windows application.  Launch and Import using the code NHT122-2.  Found, run... same problem.  The keys don't seem to align.  Switch over to the Web version... enter the number NHT122-2... not found.  Copy and paste the code directly, run... blank screen.  Try to downgrade back to 1.1... can't find the installer.  Grrr.  Literally, it's the first highlighted sample on their official blog!!!!  

Basically I'm saying that this version of BASIC suffers from a form multiple-personality disorder.  It's not 100% sure of what it actually is supposed to be.  

I'm so disappointed with this version of BASIC because it truly holds so much promise that it just falls so short of.  
Outside of the bad decisions around the "language"  implementation... the web-based "IDE" is awesome!  The "intellisense" approach is pretty cool.  Having easy and quick access to help is great.  Encouraging (and having it built in) the ability to share samples/code.  Top-level code (removal of the ceremony of VB.NET)... awesome!  Like I said... if it weren't for some seriously bad things... this would be awesome!  

**END RANT!!**

## IDE

- [Small Basic v1.2 Download](https://download.microsoft.com/download/3/6/8/3684D9A0-C25C-4F50-96E2-2BB1DFA146E7/SmallBasic.msi)
- [Small Basic Online Editor](https://smallbasic-publicwebsite.azurewebsites.net/Program/Editor.aspx)

## How-To's

- [Official Tutorials](https://smallbasic-publicwebsite.azurewebsites.net/Pages/Tutorials/Tutorials.aspx)

## Communities

- [Official Blog](https://techcommunity.microsoft.com/t5/Small-Basic-Blog/bg-p/SmallBasic)
- [Official Blog (before being moved.)](https://blogs.msdn.microsoft.com/smallbasic/)

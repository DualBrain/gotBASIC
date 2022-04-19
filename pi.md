[Home](https://gotbasic.com) • [VB 7+](vb.md) • [VB 1-6](vb6.md) • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

# Raspberry Pi (RaspPi)

- [Raspberry Pi (Official)](https://www.raspberrypi.org/)
- [Boot to BASIC](https://popey.com/blog/2021/01/raspberry-pi-boot-to-basic)

## Visual Basic via .NET Core

For the most part, discussions in this section are going to be specific to Pi4 running [Raspbian](https://www.raspbian.org) and Visual Basic as it exists through [.NET Core](https://dotnet.microsoft.com). At the time of this writing the official release of .NET Core is v3.1; v5 is "just around the corner".

There are basically two paths to *developing* for Pi; one is to use another PC (Windows 10 for example) and the other is developing directly on the Pi.  

### Using Windows 10

- [Visual Studio 2019](https://visualstudio.microsoft.com/vs/): I prefer the *Community Edition*: from what I understand it is free for personal use,, small project/team use (5 or less in size) and or active contribution to open source.  Hint: This website is actually open source; please feel free to contribute via github. ;-)  When you install, be sure to select *.NET desktop development* and *.NET Core cross-platform development*.
- [GTK# for .NET](https://www.mono-project.com/download/stable/): Note: Do not need to install Mono; just click the *Download Gtk#* "button".

### Using Raspbian

- [.NET Core](https://docs.microsoft.com/en-us/dotnet/core/install/linux-debian) or this [HowTo](https://elbruno.com/2019/12/30/raspberypi-how-to-install-net-core-3-1-in-a-raspberry-pi-4/)
- [How to install Visual Studio Code on a Raspberry Pi 4 in minutes (Scott Hanselman)](https://www.hanselman.com/blog/HowToInstallVisualStudioCodeOnARaspberryPi4InMinutes.aspx): Please note that the build for this is actually targeting *stretch*, not *buster* - but seems to work just fine.
- [VB.NET Grammar and Snippets for VSCode](https://marketplace.visualstudio.com/items?itemName=gordonwalkedby.vbnet): This provides the appropriate *experience* for writing Visual Basic since the *out-of-the-box* experience, well to put it plainly, sucks.
- (Todo) Need to verify, validate, update regarding the installation of GTK.
- (Todo) Need to provide instructions for *patching* the VSCode installation so that you can launch using "code" instead of "code-oss".
- (Todo) Need to provide instructions for *modifying* the terminal instances so that the *path* stuff is automatically attached.

To make things simpler (since I prefer to develop on Windows 10), I also setup remote desktop from Windows 10 to Pi4 following the instructions for *Remote desktop with xrdp* using [this](https://raspberrytips.com/remote-desktop-raspberry-pi/).

### Building a GUI-style Application

The following instructions are an overview (500 mile high) set of actions you must do regardless of whether or not you are developing using Visual Studio 2019 (Windows 10) or Visual Studio Code (Raspbian).

- For the first time (once), you'll need to also install [Glade](https://glade.gnome.org). For Raspbian, see [here](https://snapcraft.io/install/glade/raspbian).
- Create a regular *Console* application for .NET Core 3.1.
- Need to modify the "&lt;OutputType&gt;Exe&lt;/OutputType&gt;" to "&lt;OutputType&gt;WinExe&lt;/OutputType&gt;"
- Need to add the nuget package for "[GtkSharp](https://www.nuget.org/packages/GtkSharp)"
- Need to add the nuget package for "[System.Drawing.Common](https://www.nuget.org/packages/System.Drawing.Common/4.7.0)"

## Tutorials

- [GtkSharp - Cross Platform Toolkits (5 part series)](http://grbd.github.io/posts/2016/01/28/gtksharp-part-1-cross-platform-toolkits/)
- [ZetCode - GTK# tutorial](http://zetcode.com/gui/gtksharp/)
- [ZetCode - Widgets II in GTK#](http://zetcode.com/gui/gtksharp/widgetsII/)

## Q&amp;A

- [How to check the OS version at runtime?](https://stackoverflow.com/questions/5116977/how-to-check-the-os-version-at-runtime-e-g-on-windows-or-linux-without-using)
- [Glade Multiple Window Project](https://stackoverflow.com/questions/54853986/glade-gtkmm-multiple-window-project)
- [Can't center dialog window above main window when using Glade (Quickly)](https://askubuntu.com/questions/186587/cant-center-dialog-window-above-main-window-when-using-glade-quickly)
- [Open subwindow in GTK3](https://stackoverflow.com/questions/22747195/open-subwindow-in-gtk3)
- [Make GTK widget fill parent window](https://stackoverflow.com/questions/29985323/make-gtk-widget-fill-parent-window)
- [How do I access GUI (GTK) from multi threads?](https://stackoverflow.com/questions/2548200/how-do-i-access-gui-gtk-from-multi-threads)

## Helpful Links

- [5 ways to remote desktop on Raspberry Pi (Windows/Linux/Mac)](https://raspberrytips.com/remote-desktop-raspberry-pi/)
- [Barrier - Software KVM](https://github.com/debauchee/barrier/releases/tag/v2.3.2)
- [How To Install Visual Studio Code on a Raspberry Pi 4 In Minutes](https://www.hanselman.com/blog/HowToInstallVisualStudioCodeOnARaspberryPi4InMinutes.aspx)
- [Discussion of "Move UI from WinForms to GTK#"](https://github.com/KSP-CKAN/CKAN/issues/1840)
- [An introduction to GUI building with Glade (PDF)](https://www-uxsup.csx.cam.ac.uk/courses/moved.Glade/course.pdf)

## For future research

- [Convert a GTK application to a Qt application](https://madebyryan.blogspot.com/2011/07/convert-gtk-application-into-qt.html)
- [QtSharp (GitHub)](https://github.com/ddobrev/QtSharp)
- [QtSharp (GitLab)](https://gitlab.com/ddobrev/QtSharp)
- [Cross Platform WinForms (Kinda)](https://dotnetcoretutorials.com/2018/03/19/cross-platform-winforms-kinda/)
- [Programming with gtkmm 3](http://transit.iut2.upmf-grenoble.fr/doc/gtkmm-3.0/tutorial/html/index.html)
- [GTK+ Reference Manual](https://developer.gimp.org/api/2.0/gtk/index.html)
- [GtkSharp: HelloWorld, second try (scroll down a little bit)](https://www.mono-project.com/docs/gui/gtksharp/hello-world/)
- [convert gtkglade to libglade for backwards compatibility](https://stackoverflow.com/questions/5599394/convert-gtkglade-to-libglade-for-a-backwards-compatibility)
- [How do I use gtk builder in C#](https://stackoverflow.com/questions/15599497/how-do-i-use-gtk-builder-in-c-sharp)
- [Glade 3.8 Win32 Binaries](http://ftp.gnome.org/pub/GNOME/binaries/win32/glade/3.8/)
- [Creating a closable tab in Mono/GTK](https://stackoverflow.com/questions/2581902/creating-a-closeable-tab-in-mono-gtk)
- [Layout management in PyGTK](http://zetcode.com/gui/pygtk/layout/) or [GTK+ layout management](http://zetcode.com/gui/gtk2/gtklayoutmanagement/)
- [Menus and toolbars in GTK+](http://zetcode.com/gui/gtk2/menusandtoolbars/)
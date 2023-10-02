[Home](https://gotbasic.com) • VB 7+ • [VB 1-6](vb6.md) • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

# Microsoft Visual Basic 7+ (.NET)

## Download

- [Microsoft Visual Studio 2022 Community Edition](https://visualstudio.microsoft.com/downloads/)

## Discord

Join us over on Discord for real-time interaction with other like minded Visual Basic enthusiasts!

- [Discord Invite](https://discord.gg/Y8EH5fF6WG)

## IL

- [Sharplab.io](https://sharplab.io/) - You can easily switch the Code dropdown to Visual Basic, type code in and instantly see what the underlying IL will be - in the browser, nothing to download.

## .NET 7

- [Status of WinForms in NativeAOT](https://codevision.medium.com/status-of-winforms-in-nativeaot-4267644b1e60)
- [Again WinForms and NativeAOT](https://codevision.medium.com/again-winforms-and-nativeaot-fd068425cc13) 

## .NET 6

- [SILK.NET](https://github.com/dotnet/Silk.NET): Silk.NET is your one-stop-shop for high-speed .NET multimedia, graphics, and compute; providing bindings to popular low-level APIs such as OpenGL, OpenCL, OpenAL, OpenXR, GLFW, SDL, Vulkan, Assimp, and DirectX. Use Silk.NET to spruce up applications with cross-platform 3D graphics, audio, compute and haptics! Silk.NET works on any .NET Standard 2.0 compliant platform, including .NET 6.0, Xamarin, .NET Framework 4.6.1+, and .NET Core 2.0+.
- [C# StringLiteralGenerator](https://github.com/ufcpp/StringLiteralGenerator)

## .NET 5

Starting this section here as of November 10, 2020 to track any interesting links as they relate to VB and .NET 5.0.

- [Announcing .NET 5.0](https://devblogs.microsoft.com/dotnet/announcing-net-5-0/)  
- [App Trimming in .NET 5](https://devblogs.microsoft.com/dotnet/app-trimming-in-net-5/)  
- [Customizing Trimming in .NET 5](https://devblogs.microsoft.com/dotnet/customizing-trimming-in-net-core-5/)  
- [Introducing the Half type!](https://devblogs.microsoft.com/dotnet/introducing-the-half-type/)  
- [Debug Your .NET Core Apps in WSL 2 with Visual Studio](https://devblogs.microsoft.com/dotnet/debug-your-net-core-apps-in-wsl-2-with-visual-studio/)  
- [.NET CLI Templates in Visual Studio](https://devblogs.microsoft.com/dotnet/net-cli-templates-in-visual-studio/)  
- [Windows Forms Designer for .NET Core Released](https://devblogs.microsoft.com/dotnet/windows-forms-designer-for-net-core-released/)  
- [Bring the best of the Web to your .NET desktop applications with WebView2](https://devblogs.microsoft.com/dotnet/bring-the-best-of-the-web-to-your-net-desktop-applications-with-webview2/)  
- [Getting started with WebView2 in Windows Forms (Preview)](https://docs.microsoft.com/en-us/microsoft-edge/WebView2/gettingstarted/winforms)
- [Support Single-File Apps in .NET 5 (github)](https://github.com/dotnet/runtime/issues/36590)  
- [Single file deployment and executable](https://docs.microsoft.com/en-us/dotnet/core/deploying/single-file)  
- [Enable 'generators' in the VB compiler... (16.?)](https://github.com/dotnet/roslyn/pull/49139#)
- [VisualBasic command line tests should run on netcore (16.9)](https://github.com/dotnet/roslyn/issues/49212)  
- [Source Generators: should user generators require an attribute for discovery?](https://github.com/dotnet/roslyn/issues/42566)
- [How to migrate a Windows Forms desktop app to .NET 5](https://docs.microsoft.com/en-us/dotnet/desktop/winforms/migration/?view=netdesktop-5.0)

Stuff to review...

- [Automatically find latent bugs in your code with .NET 5](https://devblogs.microsoft.com/dotnet/automatically-find-latent-bugs-in-your-code-with-net-5/)
- [New C# Source Generator Samples](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples/)  

## Microsoft (OSS)

The Roslyn .NET compiler service provides C# and Visual Basic languages with rich code analysis APIs.

- [Digging Deeper into the Visual Basic Language Strategy](https://devblogs.microsoft.com/vbteam/digging-deeper-into-the-visual-basic-language-strategy/)
- [Visual Basic Language Specification (GitHub)](https://github.com/dotnet/vblang/tree/master/spec)
- [VbLang (GitHub)](https://github.com/dotnet/vblang): The home for design of the Visual Basic .NET programming language and runtime library.
- [Roslyn (GitHub)](https://github.com/dotnet/roslyn): The **official** OSS version of VB.NET (and C#).
  - [New Language Features in VB 14 (Visual Studio 2015) (GitHub)](https://github.com/dotnet/roslyn/wiki/New-Language-Features-in-VB-14)
  - [Getting Started VB Syntax Analysis (GitHub)](https://github.com/dotnet/roslyn/wiki/Getting-Started-VB-Syntax-Analysis)
  - [Getting Started VB Semantic Analysis (GitHub)](https://github.com/dotnet/roslyn/wiki/Getting-Started-VB-Semantic-Analysis)
  - [Getting Started VB Syntax Transformation (GitHub)](https://github.com/dotnet/roslyn/wiki/Getting-Started-VB-Syntax-Transformation)
  - [How To Write a Visual Basic Analyzer and Code Fix (GitHub)](https://github.com/dotnet/roslyn/wiki/How-To-Write-a-Visual-Basic-Analyzer-and-Code-Fix)
- [QuickVB (GitHub)](https://github.com/DualBrain/QuickVB): A MS-DOS QuickBASIC/QBasic-like IDE for Visual Basic code that's powered by the .NET Compiler Platform ("Roslyn"). 
- [Microsoft.VisualBasic Runtime Reference Source (GitHub)](https://github.com/DualBrain/referencesource/tree/master/Microsoft.VisualBasic/runtime/msvbalib)
- [Microsoft.VisualBasic.Core (GitHub)](https://github.com/dotnet/runtime/tree/master/src/libraries/Microsoft.VisualBasic.Core)
- [Tracking the progress of porting VB Runtime to .NET Core](https://github.com/dotnet/corefx/issues/31181)
- [Visual Basic in .NET Core 3.0 (Plan)](https://devblogs.microsoft.com/vbteam/visual-basic-in-net-core-3-0/)
- [Mono Linker - ILLink.Tasks](https://github.com/mono/linker/blob/master/src/ILLink.Tasks/README.md)
- [.NET Core SDK "Nighlies"](https://github.com/dotnet/core-sdk/blob/master/README.md#installers-and-binaries)
- [Select appropriate VB runtime by default #3415](https://github.com/dotnet/sdk/pull/3415)
- [Features of a pattern matching syntax #337](https://github.com/dotnet/vblang/issues/337)
- [.NET Core RID Catalog](https://docs.microsoft.com/en-us/dotnet/core/rid-catalog)
- [WinForms (.NET Core) Samples](https://github.com/dotnet/samples/tree/master/windowsforms)
- [Use the Windows Compatibility Pack to port code to .NET Core](https://docs.microsoft.com/en-us/dotnet/core/porting/windows-compat-pack)
- [WindowCommunityToolkit](https://github.com/windows-toolkit/WindowsCommunityToolkit): The Windows Community Toolkit is a collection of helper functions, custom controls, and app services. It simplifies and demonstrates common developer tasks building UWP apps for Windows 10. The toolkit is part of the .NET Foundation.
- [MAUI](https://github.com/dotnet/maui): MAUI is the .NET Multi-platform App UI, a framework for building native device applications spanning mobile, tablet, and desktop. [Introduction](https://devblogs.microsoft.com/dotnet/introducing-net-multi-platform-app-ui/)

## Online

- [Visual Basic on RexTester.com](https://rextester.com/l/visual_basic_online_compiler)

## Good Reads

- [An Exhausting List of Differences Between VB.NET & C# by Anthony D. Green](https://anthonydgreen.net/2019/02/12/exhausting-list-of-differences-between-vb-net-c/)
- [The Many Cases of ByRef by Jared Par](https://blog.paranoidcoding.com/2010/01/21/the-many-cases-of-byref.html)
- [Deterministic builds in Roslyn by Jared Par](https://blog.paranoidcoding.com/2016/04/05/deterministic-builds-in-roslyn.html)
- [Windows Forms Visual Inheritance](https://docs.microsoft.com/en-us/dotnet/framework/winforms/advanced/windows-forms-visual-inheritance)
- [Building web API apps on ASP.NET Core 2 and VB.NET](https://gunnarpeipman.com/aspnet/aspnet-core2-vbnet-weather-api/)
- [Building ASP.NET Core web apps with VB.NET](https://dotnetthoughts.net/building-aspnet-core-apps-with-vbnet/)

## People

The following people are either people who are (or have) worked on Visual Basic (.NET / .NET Core) or who are individuals who actively advocate / promote it's usage by providing samples, projects, public speaking, etc.

- [Anthony D. Green](https://anthonydgreen.net/) ([blog](https://anthonydgreen.net/), [github](https://github.com/AnthonyDGreen))
- [Cory Smith](https://addressof.com) ([blog](https://addressof.com), [github](https://github.com/dualbrain))
- Paul M. Cohen ([github](https://github.com/paul1956))
- [Xavier Flix]() ([blog](https://whenimbored.xfx.net/), [github](https://github.com/morphx666))

If you would like to be added to this list, please feel free to either contact me or create a pull request. ;-)

## How-To's

- [Converting C# to VB](csharp.md)
- [Setting up Raspian and .NET Core 2.0 on a Raspberry Pi](https://blogs.msdn.microsoft.com/david/2017/07/20/setting_up_raspian_and_dotnet_core_2_0_on_a_raspberry_pi/)
- [Get Started with Video Game Development using PuppyBreath (see Components section)](https://social.msdn.microsoft.com/Forums/en-US/2440752f-66e5-4995-93c4-e018ce43efc9/how-to-get-started-with-video-game-development-in-visual-basic-net-using-the-puppybreath?forum=vbgeneral)
- [GdiGaming GDI+ Gaming API (see Components section)](https://social.msdn.microsoft.com/Forums/vstudio/en-US/8cb8d926-6f79-41d2-a906-edf1c1aab650/gdi-gaming-api-gdigaming-ctp-1?forum=vbgeneral)
- [How to Create Video Games in VB.Net (Windows Forms)](https://social.technet.microsoft.com/wiki/contents/articles/17358.how-to-create-video-games-in-vb-net-windows-forms.aspx)
- [Retrieve Email and Parse Email in VB.NET - Tutorial](https://www.emailarchitect.net/eagetmail/kb/vbnet.aspx?cat=0&fbclid=IwAR378eNRnqo3ZmdNfiESKPARHRlV6OniIxki9Wqujn8HMrzpLaEQBquvzmQ)
- [Packaging a .NET Core 3.0 application with MSIX](https://techcommunity.microsoft.com/t5/Windows-Dev-AppConsult/Packaging-a-NET-Core-3-0-application-with-MSIX/ba-p/386432)
- [How to: Parse JSON using .NET or .NET Core – Intro](https://backtovisualbasic.net/how-to-parse-json-using-net-or-net-core/amp/)
- [How to port desktop applications to .NET Core 3.0](https://devblogs.microsoft.com/dotnet/how-to-port-desktop-applications-to-net-core-3-0/)
- [.NET Core Workers as Windows Services](https://devblogs.microsoft.com/aspnet/net-core-workers-as-windows-services/?utm_source=t.co&utm_medium=referral)
- [Select the Visual Basic language version](https://docs.microsoft.com/en-us/dotnet/visual-basic/language-reference/configure-language-version)
- [How to: Inherit Windows Forms](https://docs.microsoft.com/en-us/dotnet/framework/winforms/advanced/how-to-inherit-windows-forms)
- [Migration to ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/migration/?view=aspnetcore-2.2#aspnet-to-aspnet-core)
- [FTP](https://docs.microsoft.com/en-us/dotnet/framework/network-programming/ftp)
- [Google Drive API how to VB.NET File Download (StackOverflow)](https://stackoverflow.com/questions/56931300/google-drive-api-how-to-vb-net-file-download)
- [How to add watermark to PDF](https://www.syncfusion.com/kb/9072/how-to-add-watermark-to-pdf-file-in-c-vb-net?fbclid=IwAR2rHxCIGeiFCTqKs2tln5it-3Dliq4rdNsFcej3DSGjsMbYVAjyO2Hs5Mc)

## Video Tutorials

- Bob Tabor
  - [Visual Basic Fundamentals for Absolute Beginners using Visual Studio 2015 (Microsoft Virtual Academy)](https://mva.microsoft.com/en-us/training-courses/visual-basic-fundamentals-for-absolute-beginners-16507?l=0L9k5dpxC_104513192): Note: I skip the first episode; mainly because it "bugs" me that the whole time we are being introduced to VB, it looks like the course is all about C#. (I've also had a lot of people tell me it's the wrong link because of this.)
  - [Visual Basic Fundamentals for Absolute Beginners using Visual Studio 2015 (YouTube 8:59:09)](https://www.youtube.com/watch?v=oO9hUb14O-I): Note: Skip ahead to about minute 14.
- [Visual Basic 2010 Tutorial 200 Part Series (YouTube)](https://www.youtube.com/watch?v=mM3zB3QWuv8&list=PLC601DEA22187BBF1)
- [SchoolFreeware.com](https://www.schoolfreeware.com)
  - [Visual Basic 2010 Express 46 Part Series](https://www.schoolfreeware.com/Visual_Basic_2010_Express_Tutorials_-_VB.Net_-_Beginning_-_Game_Programming.html)
  - [Visual Basic 2010 Express 46 Part Series (YouTube)](https://www.youtube.com/playlist?list=PL86A8013B8782A7AD)
  - [Visual Basic 2012 Express 13 Part Series](https://www.schoolfreeware.com/Visual_Basic_Express_2012_For_Windows_Desktop_Tutorials.html)
- [Sonar Learning's Visual Basic Programming 200 Part Series (20 hours)](https://sonarlearning.co.uk/coursepage.php?topic=desktop&course=ext-visual-basic)
- [Visual Basic Tutorial 2017 (YouTube 29:04)](https://youtu.be/3FkWddODLno)
- [Learn Visual Basic in 30 Minutes (YouTube 31:18)](https://www.youtube.com/watch?v=gcFHyVYdeFU&t=36s)
- [Learn Visual Basic Advanced 2015 (YouTube 39:04)](https://www.youtube.com/watch?v=oWRxt48lRzo&t=15s)
- [VbPage (Facebook)](https://www.facebook.com/VbPagetut/?__tn__=%2CdkCH-R-R&eid=ARBUCwFpXoA32t0O1yzMKQqMLOloovOoY1YDC-5ssFMEodKCa5YdaTQhwtmceH_4-dwP_WOh8MRk1KZY&hc_ref=ART9mFM0cfhNGxixAiWdRbVIqNM22AMGc-45q53herZ2fWt6apskSngHrOX-ojnBrec&fref=nf&hc_location=group)

## Communities

- [Visual Basic Discord Server (Invite)](https://discord.gg/Y8EH5fF6WG)
- [VB.NET Gitter](https://www.gitter.im/VB-NET)
- Facebook
  - [Visual Basic .NET](https://www.facebook.com/groups/public.module/)
  - [VB.NET Developers](https://www.facebook.com/groups/vbnetdevelopers/)
  - [VB.net CODERS International Group](https://www.facebook.com/groups/vbcoders/)
  - [Visual Basic Group](https://www.facebook.com/groups/visualbas/)
  - [VB.Net C# Programmers](https://www.facebook.com/groups/252300688263578/)

### User Groups

- [.NET Developer Community](https://dotnet.microsoft.com/platform/community): Meet like-minded developers, connect with the .NET team, find podcass, and more.
- Florida
  - [Boca Raton, FL FlaDotNet (Meetup)](https://www.meetup.com/FlaDotNet/events/)
- Texas
  - [Dallas .NET Users Group (Facebook)](https://www.facebook.com/groups/228879463971959/)
  - [Fort Worth .NET Users Group (Facebook)](https://www.facebook.com/groups/FWDNUG/)
  - [NRH BASIC SIG (North Richland Hills BASIC Special Interest Group)](http://basicsig.com/)

## Components

- [WebView2](https://devblogs.microsoft.com/dotnet/bring-the-best-of-the-web-to-your-net-desktop-applications-with-webview2/): Bring the best of the Web to your .NET desktop applications.
- [AGKSharp for Windows](http://madbit.bplaced.com/?page_id=136): With AGKSharp you have the chance to write AppGameKit programs in the language C# and in VisualBasic.
- [PuppyBreath by Reed Kimble (GitHub)](https://github.com/ReedKimble/PuppyBreath): A simplistic and robust video game engine for .NET Windows Forms projects, based entirely on managed code and GDI+ graphics.
- [GdiGaming API by Reed Kimble (CodePlex)](https://archive.codeplex.com/?p=gdigaming): GDI+ based .NET Game Engine.
- [DotNetBrowser - Integrate a Chromium-based browser with your .NET app. (Commercial)](https://www.teamdev.com/dotnetbrowser)
- [FirmataVB](http://www.acraigie.com/programming/firmatavb/default.html): Easily take advantage of the Firmata protocol (Arduino).

## Tools

- [dnSpy (GitHub)](https://github.com/0xd4d/dnSpy): .NET debugger and assembly editor.
- [ConnectionStrings.com](https://www.connectionstrings.com/): Helps developers connect software to data.

## Analyzers

- [Write Better Code Faster with Roslyn Analyzers](https://devblogs.microsoft.com/dotnet/write-better-code-faster-with-roslyn-analyzers/)
- [code-cracker (GitHub)](https://github.com/code-cracker/code-cracker): An analyzer library for C# and VB that uses Roslyn to produce refactorings, code analysis, and other niceties. http://code-cracker.github.io/
- [DotNetAnalyzers (GitHub)](https://github.com/DotNetAnalyzers/DotNetAnalyzers): This project is for the community to make a common code base of .NET code analyzers using the new VS14 code analyzer functionality. 
- [VBSttyleAnalyzer (GitHub)](https://github.com/mrlacey/VBStyleAnalyzer): Roslyn analyzers for VB UWP apps.
- [DelSole.CrossAnalyzers (GitHub)](https://github.com/AlessandroDelSole/DelSole.CrossAnalyzers): A collection of analyzers and refactorings for C# and Visual Basic on multiple platforms. [*](https://github.com/amberdextrous/DotNetAnalyzers), [**](https://github.com/DualBrain/DotNetAnalyzers)
- [DotNetAnalyzers (GitHub)](https://github.com/Urmel11/DotNetAnalyzers): No additional comments available.
- ["VBAnalyzers" search on GitHub](https://github.com/search?l=Visual+Basic&q=Imports+Microsoft.CodeAnalysis.VisualBasic.Syntax&type=Code): This search link was shared with me; need to spend some time investigating through the results to find the "best of the best".

## "My"

- [Extending the My namespace](https://www.codeproject.com/articles/28979/extending-the-my-namespace)
- [Getting Started with My.Blogs](https://docs.microsoft.com/en-us/previous-versions/ms364056(v=vs.80)): My.Blogs is a collection of sample code that will show you how you can easily provide programmatic access to weblogs in the applications you build. Full source code is provided along with Windows Forms, ASP.NET 2.0, and a Visual Studio 2005 Tools for Office Outlook Add-In.
- [Package and deploy custom My extensions](https://docs.microsoft.com/en-us/dotnet/visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions)
- [Customizing Projects and Extending My](https://docs.microsoft.com/en-us/dotnet/visual-basic/developing-apps/customizing-extending-my/)
- [Extending the My Namespace](https://docs.microsoft.com/en-us/dotnet/visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace)


## Samples

- [VB Dev2Dev (GitHub)](https://github.com/VBDev2Dev)
- [Karen Payne's Visual Basic Getting Started (GitHub)](https://github.com/karenpayneoregon/visual-basic-getting-started)
- [AdvanceRichTextBox with line numbers (GitHub)](https://github.com/paul1956/AdvanceRichTextBox)

## Gists

- [Anthony D. Green](https://anthonydgreen.net/)
  - [GameLoop](https://gist.github.com/AnthonyDGreen/c2a29f8e59990c2ad613f22a779ac60e?fbclid=IwAR31yd9vgHOyzJsmRj6A0LWTPYcqCpxWaCUbYWwr2vjibquFG51YcIxx7rY)

## Where there's a will...

Although Microsoft has done a great job with several technology stacks; there are a few areas where support falls a little short or just doesn't seem to exist.  This section points to areas where you can find "how to make it (mostly) work in VB".

- [Mohammad Hamdy Ghenem (@VBAndCs)](https://github.com/VBAndCs)
  - [VB Flag Auto Generator (github)](https://github.com/VBAndCs/VB-Flag-auto-generator)
  - [VB Record Generator (github)](https://github.com/VBAndCs/VB-Record-Generator)
  - [Vazor - A VB.NET Razor for ASP.NET Core 3.0 MVC and Razor Pages.](https://github.com/VBAndCs/Vazor)  
- ILMerge
  - [ILMerge](https://www.microsoft.com/en-us/download/details.aspx?id=17630): ILMerge is a utility for merging multiple .NET assemblies into a single .NET assembly. It works on executables and DLLs alike and comes with several options for controlling the processing and format of the output.  
  - [ILMerge-GUI, the .NET merger](https://archive.codeplex.com/?p=ilmergegui)
  - [.NET whole application in a single .exe file? (stackoverflow)](https://stackoverflow.com/questions/3261942/net-whole-application-as-a-single-exe-file)
- .NET Core - Note: Microsoft is committed to VB on .NET Core; but we are still currently in the very beginning stages of this.  As such, most of the following related to .NET Core and WinForms isn't (currently) related to VB.
  - [Getting started with WinForms for .NET Core](https://github.com/dotnet/winforms/blob/master/Documentation/getting-started.md)
  - [Are your Windows Forms and WPF applications ready for .NET Core 3.0?](https://devblogs.microsoft.com/dotnet/are-your-windows-forms-and-wpf-applications-ready-for-net-core-3-0/)([GitHub](https://github.com/microsoft/dotnet-apiport-ui))
  - [Porting existing applications to .NET Core 3.0 (GitHub)](https://github.com/dotnet/winforms/blob/master/Documentation/porting-guidelines.md)
  - [How to port desktop applications to .NET Core 3.0](https://devblogs.microsoft.com/dotnet/how-to-port-desktop-applications-to-net-core-3-0/)
  - [How to Port Desktop Applications to .NET Core 3.0 (YouTube)](https://www.youtube.com/watch?v=upVQEUc_KwU)
  - [.NET Core 3.0 Windows Forms Samples (GitHub)](https://github.com/dotnet/samples/tree/master/windowsforms)
  - [Performance Improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-core-3-0/)
  - [Announciing .NET Core 3.0 Preview 5](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
  - [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/?fbclid=IwAR1kZtAt1AXL8DpEtF9uYtlRv2xXk4fyXXOMVIav3MLKLM2vWRgPuIgGE7I)
- WebAssembly
  - [A Very Basically VB.NET WebAssembly Compiler](https://github.com/GCModeller-Cloud/data.ts/releases/tag/v0.5.136-alpha)
- Xamarin
  - [Visual Basic and .NET Standard](https://docs.microsoft.com/en-us/xamarin/cross-platform/platform/visual-basic/index)
  - [Xamarin.Forms using Visual Basic.NET](https://docs.microsoft.com/en-us/xamarin/cross-platform/platform/visual-basic/xamarin-forms)
  - [Visual Basic.NET in Xamarin iOS and Android](https://docs.microsoft.com/en-us/xamarin/cross-platform/platform/visual-basic/native-apps)
  - [Portable Visual Basic.NET](https://docs.microsoft.com/en-us/xamarin/cross-platform/platform/visual-basic/)
  - [Mobile Apps with Visual Basic & Xamarin.Forms](https://devblogs.microsoft.com/xamarin/mobile-apps-with-visual-basic-xamarin-forms/)
  - [Official Xamarin Samples (GitHub)](https://github.com/xamarin/mobile-samples/tree/master/VisualBasic)
    - [XamarinFormsVB (GitHub)](https://github.com/xamarin/mobile-samples/tree/master/VisualBasic/XamarinFormsVB)  
    - [TaskyVB (GitHub)](https://github.com/xamarin/mobile-samples/tree/master/VisualBasic/TaskyVB)  
  - [Add full VB Support to Xamarin in 2018. (GitHub)](https://github.com/dotnet/vblang/issues/238)
- [Razor](https://docs.microsoft.com/en-us/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-vb)  
  - [Vazor - A VB.NET Razor for ASP.NET Core 3.0 MVC and Razor Pages.](https://github.com/VBAndCs/Vazor)  
  - [A VB.NET Razor for ASP.NET Core 2.2 MVC and Razor Pages.](https://github.com/VBAndCs/Vazor-DotNetCore2)  
- [Blazor](https://blazor.net) - CAUTION: Seriously bleeding edge here... much of this isn't VB.  
  - [Getting Started with Blazor (YouTube)](https://www.youtube.com/watch?v=bbHzyIsqGuU&list=PL8h4jt35t1whukdnbIMpAEWmL4h1XABaa)  
  - [Blazor Dual-Mode Example (GitHub)](https://github.com/Suchiman/BlazorDualMode)  
- Web UI Alternatives
  - [DotVVM (GitHub)](https://github.com/riganti/dotvvm): Open Source MVVM framework for Web Apps (https://www.dotvvm.com).  
  - [Nancy (GitHub)](https://github.com/NancyFx/Nancy): Lightweight, low-ceremony, framework for building HTTP based services on .NET and Mono (http://nancyfx.org).  
- [VB6 vs VB.NET Language](http://www.vbmigration.com/Resources/migratingfromvb6.aspx)
- [VB.NET Grammars and Snippets
 for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=gordonwalkedby.vbnet)

## COOL PROJECTS!!!!

- [Anthony D. Green](https://anthonydgreen.net/)
  - [We have XML Literals; how about JSON Literals?](https://anthonydgreen.net/2019/03/11/json-aficionados-wanted/)([Video](https://www.youtube.com/watch?v=4-tEq-5VVHc))
  - [Enhanced For Each Loops](https://anthonydgreen.net/2019/02/20/maybe-enhancing-for-each-loops-with-linq/)([Video](https://www.youtube.com/watch?v=ynBHLuicCYs))
- [Xavier Flix](https://whenimbored.xfx.net)
  - [A VB.NET implementation of an almost working 8086 emulator.](https://github.com/morphx666/x8086NetEmu)
  - [A software based Oscilloscope / Vectorscope](https://github.com/morphx666/SoftScope)
  - [Network traffic monitor for Windows.](https://github.com/morphx666/NetworkMonitor)
  - [VBBrainF.NET - BrainF--f interpreter, compiler, debugger and converter implemented in VB.NET](https://github.com/morphx666/VBBrainF.NET)
- [A program to convert C# source code to VB](https://github.com/paul1956/CSharpToVB)
  - [Simple face detection using Emgu.CV](https://github.com/morphx666/FaceDetection)
  - [Text Parallax and water ripple effects.](https://github.com/morphx666/Parallax)
  - [An image to ASCII art converter.](https://github.com/morphx666/ASCIIArt)
  - [Simple synthesizer written in VB.NET](https://github.com/morphx666/PianoBizarre)
  - [MP3 decoding library written in VB.NET](https://github.com/morphx666/vbMP3decoder)
  - [Simple 3D rendering engine entirely written in VB.NET](https://github.com/morphx666/3DEngine)
- [VbRogue - A community-based-project Rogue clone written in Visual Basic.](https://github.com/DualBrain/VbRogue)
- [Apress - Build Your Own .NET Language and Compiler by Edward G. Nilges (Code)](https://github.com/Apress/build-your-own-.net-language-compiler)
- [Cory Smith](http://addressof.com)
  - [BASIC for .NET (GitHub)](https://github.com/dualbrain/basic)
  - [Checkers Solitaire - An original game inspired by a game written circa 1978 by David H. Ahl. (GitHub)](https://github.com/DualBrain/CheckersSolitaire)
  - [Solitaire - Clone of Microsoft Windows Solitaire circa Windows XP. (GitHub)](https://github.com/DualBrain/Solitaire)
- [ExpressionToString by Zev Spitz (GitHub)](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees): String representation of expression trees and expression tree parts + debugging visualizer.
- [dotNetTips.Utility by David McCarter (GitHub)](https://github.com/RealDotNetDave/dotNetTips.Utility): Common .NET code David McCarter has been writing since it was released that features C#, VB.NET, Portable Libraries, Logging, .NET Core.

## GitHub Projects

- [VBAsyncEnumerableHelper](https://github.com/Nukepayload2/VBAsyncEnumerableHelper): Provides helpers for consuming BCL Async interfaces with VB.

## Additional Resources / Related Information

- [Microsoft WinForms .NET Core UI Framework (GitHub)](https://github.com/dotnet/winforms): Windows Forms is a .NET Core UI framework for building Windows desktop applications. 
- [Microsoft WPF .NET Core UI Framework (GitHub)](https://github.com/dotnet/wpf): WPF is a .NET Core UI framework for building Windows desktop applications.
- [Microsoft UI Library (GitHub)](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md)
- [C#]
  - [VB and C# Equivalents](https://www.tangiblesoftwaresolutions.com/vb-and-csharp-equivalents.html)
  - [C# to VB Conversion Tips](https://www.tangiblesoftwaresolutions.com/sitemap.html#csharp-to-vb)
  - [Tangible Software Solutions Instant VB (Commercial)](https://www.tangiblesoftwaresolutions.com/product_details/csharp-to-vb-converter.html): Instant VB produces great VB.NET code, saving you hours of painstaking work and valuable time.
  - [developerFusion Convert C# to VB.NET (Free)](https://www.developerfusion.com/tools/convert/csharp-to-vb/): Simply paste in your C# code below, and this free utility will automatically convert it to its equivalent in VB.NET. 
  - [Telerik Code Converter by Progress (Free)](http://converter.telerik.com/): Convert code from C# to VB and from VB to C#.
 - [.NET Core Daily Builds -- Servicing and future releases](https://github.com/dotnet/core/blob/master/daily-builds.md)
- Database
  - [SQLite/SQL Server Compact Toolbox](https://marketplace.visualstudio.com/items?itemName=ErikEJ.SQLServerCompactSQLiteToolbox&fbclid=IwAR3-pzhs47PHm4c9Vd4-HvfFd-dfSeatWfnW4Iho2n3m_eRnuHMjWdbierQ): SQLite / SQL Server Compact Toolbox extension for Visual Studio. This extension adds several features to help your embedded database development efforts: Scripting of tables and data, import from SQL Server and CSV files and much, much more.
- [Mono Visual Basic support](https://www.mono-project.com/docs/about-mono/languages/visualbasic/): Visual Basic.NET support in Mono. The Visual Basic runtime has been available for Mono for a while, and with the release of Mono 1.2.3, the Visual Basic support is complete, with the introduction of a self-hosting compiler and class libraries for Visual Basic development on any of the Mono supported systems.  
- [gRPC for .NET (GitHub)](https://github.com/grpc/grpc-dotnet)
- [SlackNet](https://github.com/soxtoby/SlackNet): A comprehensive Slack API client for .NET.
- [VSCode extension for CS-Script (GitHub)](https://github.com/oleg-shilo/cs-script.vscode): 
- [WasmWinforms (GitHub)](https://github.com/roozbehid/WasmWinforms)
- [NuGet Must Haves](https://nugetmusthaves.com/): Helps you find the best NuGet packages!

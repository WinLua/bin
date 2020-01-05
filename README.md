# bin
Binaries and Installers for public consumption. Please see [Wiki Home](https://github.com/WinLua/bin/wiki) for release notes. If you wandered in here looking for an OpenSSL binary, check the LibreSSL directory for a 32 bit msi (or download WinLua!). 

## Getting Started
If you just want to try Lua on Windows 10+, download the Release 1 version of the Lua 5.3 installer. The new *Alpha* Release 3 file is a more complete installer with the Luarocks package manager, LibreSSL and a Lua based build system for C called JamPlus. 

## What's Included
Both Releases will install Lua, plus a de-facto filesystem component and a C++ interface called Sol(2/3). Release 1 provides 32 and 64 bit, Release 3 is currently 32 bit only.[1]. After installation Lua can be used from the command line (any current cmd or powershell windows will need to be re-opened) or by opening your start menu and typing "Lua" and clicking on the icon. If you want to use LuaRocks, you'll need a compiler, which is discussed below. 

## Debugging Lua with Visual Studio Code
The Release 3 Lua binaries contain a patch file that allows for more performant debugging by adding a non-standard Lua op-code. This patch can be used in conjunction with the DevCat Debugger for Visual Studio Code.

The original op_halt patch was authored by Dan Tull. This version is made available by DevCat here: 
https://github.com/devcat-studio/lua-5.3.4-op_halt

The DevCat debugger is made available here:
https://marketplace.visualstudio.com/items?itemName=devCAT.lua-debug

Visual Studio Code can be downloaded here: https://code.visualstudio.com/Download

## C/C++ Compiler
Some components available on LuaRocks require a C/C++ compiler to build and use. I currently use the Microsoct Visual C++ compilers. They are included with Visual Studio (including the FREE community edition), but VS is a 20 GB download. If you are looking for a more practical command line toolchain (~4 GB), you can download the FREE VC++ compiler toolchain. The microsoft download is here: 
https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16

There is an excellent windows package manager calle Chocolatey. The build tools are available through the choco interface:

`choco install visualstudio2019buildtool`

https://chocolatey.org/packages/visualstudio2019buildtools

The VC redistributable is here:
https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads

## Using LuaRocks from Powershell

Luarocks requires a compiler to build and install rocks but Powershell isn't configured to work with the compilers by default. To fix this, I've included a powershell version of vsvar.bat called vsvars.ps1. If you are willining and able to run `Set-ExecutionPolicy Unrestricted` you can include the vsvars.ps1 file in your "...\Documents\WindowsPowerShell" folder and add the following line to your Microsoft.PowerShell_profile.ps1 file (Where the year is the version of Visual Studio or VC build tools):

```powershell

write-host 'Load VsVars...'
. $PSScriptRoot/vsVars.ps1 2019
```

Next time you run powershell you can check for a compiler by typing `cl`

## Lua Resources?

Do yourself a favor and go buy the Programming In Lua book. https://www.lua.org/pil/

The Lua-Users wiki is also a great place to start. http://lua-users.org/wiki/ [2] 

## Other Binary Solutions

### ZeroBrane Studio
I love ZeroBrane. If you are looking for an excellent Integrated Development Environment (IDE) akin to Visual Studio for Lua - repleat with tons of samples and tutorials - then please download and support https://studio.zerobrane.com. If you're new to Lua, I recommend it. This project and ZeroBrane are not configured to work togther (though ZeroBrane is configurable) but it doesn't matter. ZeroBrane comes with a wide range of "Lua flavours" including the current Lua version. I highly recommend ZeroBrane.

*The WinLua project is no a replacement for ZeroBrane. ZeroBrane is a far more complete Lua solution for beginners.*

### LuaBinaries
[LuaBinaries](https://sourceforge.net/projects/luabinaries/) is an excellent, current distribution of Lua built with GCC (GNU C Compiler) on MinGW (Minimum GNU for Windows) [3]. It's an excellent distribution if you already know the ins and outs of Lua and you'd like to include the executables with your application and know how to manipulate the windows PATH variable. LuaBinaries is also available through the [Choclatey package manager](https://chocolatey.org). 

### JoeDF
JoeDf has [lots of goodies built with MinGW](http://joedf.ahkscript.org/LuaBuilds/); his site explains how to use them. Binaries are packaged as zips and there is no path manipulation.

## WinLua By Contrast

WinLua by contrast is built with Visual Studio 2017 against Window 10. WinLua only officially supports Windows 10, but can be used if you download the VC Redtistributable[2]. The binaries are "integrated with Windows" via installers and so Lua can be added and removed like other applications and used from the command line. The luaxx.dll can be dynamically included in applications from a standardized location. If using C++, [Sol2 can be used with a single include](https://github.com/WinLua/bin/wiki/Release-1#sol2). WinLua Release 1 is also available as a Merge Module for inclusion in third party installers (e.g. your installer built with [ISWix](https://github.com/iswix-llc/iswix-tutorials) ) but is not yet availale on choclatey. I hope to have a bootstrapper soon to allow for MSVC re-distribution.


 [1] If you don't know why you would want 64 bits then you don't need them. The 32 bit version is in no way inferior for your purposes and simplifies things when Lua starts getting complicated. Big numbers are there for Mathematicians, not us.
 
 [2] https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads
 
 [3] To learn more about GNU environment on Windows, see MSYS2 and the excellent MSYS2 installer in choclatey.

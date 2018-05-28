# bin
Binaries and Installers for public consumption. Please see [Wiki Home](https://github.com/WinLua/bin/wiki) for release notes. If you wandered in here looking for an OpenSSL binary, check the LibreSSL directory for a 32 bit msi (or download WinLua!). 

## Getting Started

If you just want to try Lua on Windows 10+, download the Release 1 32 Bit version of the Lua 5.3 installer[1]. If your looking for Lua 5.4, please check out the Release 2 directory, which is currently an experimental release. Both MSIs will install Lua, plus a de-facto standard component that allows access to the filesystem, among other things. After installation Lua can be used from the command line (any current cmd or powershell windows will need to be re-opened) or by opening your start menu and typing "Lua" and clicking on the icon. 

**No other Lua modules are available at this point. You will have to download and install LuaRocks yourself. Any Rocks that require C/C++ will require either mingw or Visual Studio (Professional?) to be installed on the computer.** *Solutions to this problem are a work in progress.*

## What about auto-complete for Lua and fancy debugging?

If you are looking for an excellent Integrated Development Environment (IDE) akin to Visual Studio for Lua - repleat with tons of samples and tutorials - then please download and support https://studio.zerobrane.com. This project and ZeroBrane are not configured to work togther out of the box, but ZeroBrane is configurable. See https://studio.zerobrane.com/doc-general-preferences (Interpreter Path). Either way, it probably won't make a difference to you. ZeroBrane comes installed with a wide range of "Lua flavours" including the current Lua version. 

*The WinLua project is not a replacement for ZeroBrane. WinLua is about bog-standard Lua.*

## Okay, I've installed Lua. What Next?

Do yourself a favor and go buy the Programming In Lua book. https://www.lua.org/pil/

The Lua-Users wiki is also a great place to start. http://lua-users.org/wiki/ [2] 


There are lots of gems out there that will be added to the wiki in time. 

## Background

There are many excellent resources for Lua on Windows but some of them are out of date, and others are too complex for the average user. The combination of these realities makes learning Lua on Windows very difficult. *I wanted a simple installer that would install and remove Lua so I could hack at it.* I've tried to introduce some of my friends to Lua that are *very* technical but are not software developers. It took them months of poking around until they found something that works. My experience has been similar. 

## Other Binary Solutions

### LuaBinaries
[LuaBinaries](https://sourceforge.net/projects/luabinaries/) is an excellent, current distribution of Lua built with GCC (GNU C Compiler) on MinGW (Minimum GNU for Windows) [3]. It's an excellent distribution if you already know the ins and outs of Lua and you'd like to include the executables with your application and know how to manipulate the windows PATH variable. LuaBinaries is also available through the [Choclatey package manager](https://chocolatey.org). 

### JoeDF
JoeDf has [lots of goodies built with MinGW](http://joedf.ahkscript.org/LuaBuilds/); his site explains how to use them. Binaries are packaged as zips and there is no path manipulation.

## WinLua By Contrast

WinLua by contrast is built with Visual Studio 2017 against Window 10. The binaries are "integrated with Windows" via installers and so Lua can be added and removed like other applications and used from the command line. The luaxx.dll can be dynamically included in applications from a standardized location. If using C++, [Sol2 can be used with a single include](https://github.com/WinLua/bin/wiki/Release-1#sol2). WinLua is also available as a Merge Module for inclusion in third party installers (e.g. your installer built with [ISWix](https://github.com/iswix-llc/iswix-tutorials) ) but is not yet availale on choclatey. I hope to have a bootstrapper soon to allow for MSVC re-distribution.

## How can I help

Contribute. Documentation is a big part of the battle. If you have a Lua project please drop an issue and say hi.
 
 [1] If you don't know why you would want 64 bits then you don't need them. The 32 bit version is in no way inferior for your purposes and simplifies things when Lua starts getting complicated. Big numbers are there for Mathematicians, not us.
 
 [2] I pretty much have this open any time I'm writting Lua: http://lua-users.org/wiki/StringLibraryTutorial
 
 [3] To learn more about GNU environment on Windows, see MSYS2 and the excellent MSYS2 installer in choclatey.

# bin
Binaries and Installers for public consumption.

## Getting Started

If you just want to try Lua on Windows 10+, download the 32 Bit version of the Lua 5.3 installer[1]. This will install the latest Lua, plus a de-facto standard component that allows access to the filesystem. Lua can now be used from the command line (any current cmd or powershell windows will need to be re-opened) or by opening your start menu and typing "Lua" and clicking on the icon. 

**No other components are available at this point. You will have to download and install LuaRocks yourself. Any Rocks that require C/C++ will require either mingw or Visual Studio (Professional?) to be installed on the computer.** *We am working towards fixing this situation.*

## What about auto-complete for Lua and fancy debugging?

If you are looking for an excellent Integrated Development Environment (IDE) akin to Visual Studio for Lua - repleat with tons of samples and tutorials - then please download and support https://studio.zerobrane.com. This project and ZeroBrane are not configured to work togther out of the box, but ZeroBrane is configurable. See https://studio.zerobrane.com/doc-general-preferences (Interpreter Path). Either way, it probably won't make a difference to you. ZeroBrane comes installed with a wide range of "Lua flavours" including the current Lua version. 

*The WinLua project is not a replacement for ZeroBrane. WinLua is about bog-standard Lua.*

## Okay, I've installed Lua. What Next?

Do yourself a favor and go buy the Programming In Lua book. https://www.lua.org/pil/

The Lua-Users wiki is also a great place to start. http://lua-users.org/wiki/ [2] 


There are lots of gems out there that will be added to the wiki in time. 

## Background

There are many excellent resources for Lua on Windows but some of them are out of date, and others are too complex for the average user. The combination of these hurdles make learning Lua on Windows and knowning what is current very difficult. *I wanted a simple installer that would install and remove Lua so I could hack at it.* I've tried to introduce some of my friends to Lua that are *very* technical but are not software developers. It took them months of poking around until they found something that the *think might* work, but... My experience has been similar. 

## What is wrong with the current solutions?

One of my goals is to outline all the Windows resources and their state of support in the Wiki. I shall elaborate there. 

That said, LuaBinaries is an excellent, current distribution of Lua built with GCC (GNU C Compiler) on MinGW (Minimum GNU for Windows). It's an excellent distribution but does not provide an installer and to the best of my knowledge requires additional MinGW resources. The binaries do not include a *.lib files that is required to link when using Visual Studio (namely LINK.exe). It's still *not quite* the Windows way...
 (to be continued)
 
 [1] If you don't know why you would want 64 bits then you don't need them. The 32 bit version is in no way inferior for your purposes and simplifies things when Lua starts getting complicated. Big numbers are there for Mathematicians, not us. 
 [2] I pretty much have this open any time I'm writting Lua: http://lua-users.org/wiki/StringLibraryTutorial

# bin
Binaries and Installers for public consumption.

This project is a collection of resources to help Windows users get started with Lua. The imputis has been my own frustration finding a straight line in using Lua with Windows 10.

## Background

There are many excellent resources for Lua on Windows but some of them are out of date, and others are too complex for the average user. I wanted a simple installer that would install and remove Lua so I could hack at it. 

## What is wrong with the current solutions?

One of my goals is to outline all the Windows resources and their state of support. 

That said, LuaBinaries is an excellent, current distribution of Lua based on MinGW (Minimum GNU for Windows). It's an excellent distribution but does not provide an installer and to the best of my knowledge requires additional MinGW resources. The binaries do not include a *.lib files that is required to link when using Visual Studio (namely LINK.exe). 

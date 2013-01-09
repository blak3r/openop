openop
======

Right click on file to copy/move it to dynamic list of open Explorer paths.  Eliminates the need to dig around in your taskbar for the other explorer window to complete your drag and drop operation.

Motivation: I find that I generally have multiple explorer windows open when I'm working on a project but they'll get hidden by other apps such as my IDE or a browser.  As a result, I end up wasting lots of time digging around in the start menu or alt-tab'in to find the explorer window I need.  This menu automatically provides a list of the currently open Explorer windows so you can copy from one to the other even when the other isn't visible!

![Mockup](http://www.blakerobertson.com/storage/perm/SmartMoveTo.png)

## How to Install

1. Open a cmd window __as administrator__
2. cd to the build directory and run one of the commands below.
3. Note: in order to test you will need to kill all explorer windows, then build the solution, then start explorer.exe again.  (You do not need to reregister the shell extension after updating the code).

### To register the Shell Extension ###
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\regasm <ProjectPath>\Release\CSShellExtContextMenuHandler.dll /codebase

### To Unregister the Shell Extension ###
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\regasm /unregister <ProjectPath>\Release\CSShellExtContextMenuHandler.dll /codebase

## Build Instructions

This project is written in C#.

1. Open the solution with Visual Studio 2010 or better.  Note: express editions will work fine but you will get errors about not being able to load the installer projects as that requires the full version of Visual Studio.
2. Note: if you register the extension from your build directory you will not be able to build until you stop all explorer windows as the dll will be in use.

## Useful Code Snippets

1. I was unable to find an example of creating a submenu for a context item.  So, if you need that this project will serve as a good reference.
2. There is code in here to get a list of all the open explorer windows and their relevant paths.
3. Useful reference for how to create a Shell Extension in C# (Managed Code).  With the release of .NET 4.0 Microsoft _originally_ said managed code could be used for Shell Extensions since the "CLR in 4.0 can be hosted side by side with other versions in the same process".  They wrote a MSDN article on how to create a managed shell extension which they later retracted because they didn't know the long term reprocussions of this approach.  I figured it was good enough for my needs and used that article as the basis for my project.

![gitimg](https://gitimg.com/blak3r/openop/readme/track)

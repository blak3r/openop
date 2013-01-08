openop
======

Right click on file to copy/move it to dynamic list of open Explorer paths.  Eliminates the need to dig around in your taskbar for the other explorer window to complete your drag and drop operation.

## How to Install

1. Open a cmd window __as administrator__
2. cd to the build directory and run one of the commands below.
3. Note: in order to test you will need to kill all explorer windows, then build the solution, then start explorer.exe again.  (You do not need to reregister the shell extension after updating the code).

### To register the Shell Extension ###
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\regasm C:\c
sharp\CSShellExtContextMenuHandler\Release\CSShellExtContextMenuHandler.dll /codebase

### To Unregister the Shell Extension ###
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\regasm /unregister C:\csharp\CSShellExtContextMenuHandler\Release\CSShellExtContextMenuHandler.dll /codebase

## Build Instructions

1. Open the solution with Visual Studio 2010 or better.  Note: express editions will work fine but you will get errors about not being able to load the installer projects as that requires the full version of Visual Studio.
2. Note: if you register the extension from your build directory you will not be able to build until you stop all explorer windows as the dll will be in use.
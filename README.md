# wxnim
Nim wrapper for wxWidgets. Most common widgets have been wrapped but it's likely
that I missed a few.

Still in development, needs way more testing!

# Installation on Linux

Install ``wxnim`` and grab the ``wxGtk`` package from your package manager. Make sure ``wx-config`` is in your PATH and executable. If you want to compile wxWidgets 3.0.2 yourself (for example in order to use X11 or link it statically into your application) you can use the ``-d:"wxWidgetsPath:<path to the folder wx-config is in>"`` flag.

# Installation on Windows

Install ``wxnim`` and point it to a compiled version of wxWidgets 3.0.2 with the ``-d:"wxWidgetsPath:<path to the folder wx-config is in>"`` flag.

Compile wxWidgets
via ``mingw32-make -f makefile.gcc SHARED=0 UNICODE=1 BUILD=release``.

More details can be found here:

https://wiki.wxwidgets.org/Compiling_wxWidgets_with_MinGW

# Examples

This module now also ships with a macro to easily create GUIs. Currently it resides with the examples, it will move to a better place soon. To see it in use look at or compile the ``controlgallery`` example with::

	cd examples

	nim cpp -r controlgallery.nim

The output of the macro should look like these images from Linux and Windows respectively:

On Linux wxWidgets uses GTK+ as it's backend and looks will vary greatly depending on theme (this screenshot is taken with the Arc theme and M+ 2p font).

![Linux](/screenshots/linux.png)

On Windows wxWidgets uses Win32 Forms, so looks might change depending on Windows version, this is from Windows 10:

![Windows](/screenshots/windows.png)

To compile the original examples::

  cd examples

  nim cpp -r example2.nim


# Generating the Nim code

This wrapper was originally generated by c2nim. To regenerate the Nim code, simply
run ``nim c -r scripts/convert``. However since the files have later been modified this would break the library. Only do this if you are developing wxWidgets and need to generate the files again.


# Todo

- Make event handling support Nim's closures.
- Make the interface even more Nim-like


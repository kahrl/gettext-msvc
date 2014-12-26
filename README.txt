Visual Studio 2013 solution for gettext-0.19.4 and libiconv-1.14
================================================================

This lets you build libintl (from gettext) and libiconv with Visual Studio 2013.
(These two libraries are just enough to build Minetest with gettext support.)

Notes:

- This repository contains neither any precompiled binaries nor the full
  source code of gettext & libiconv. See below for where to get
  the source code and how to build it.

- Output will be: libintl.dll, libintl.lib, libiconv.dll, libiconv.lib.

- None of the utilities (such as xgettext) will be built.

- This has only been tested with Visual Studio Express 2013.

- 32 bit and 64 bit builds are both supported.


Instructions
============

1. Clone this repository or extract a zipped version of it somewhere.

2. Download gettext-0.19.4.tar.gz from

     http://ftp.gnu.org/gnu/gettext/gettext-0.19.4.tar.gz

   and libiconv-1.14.tar.gz from

     http://ftp.gnu.org/gnu/libiconv/libiconv-1.14.tar.gz

3. Extract them both into the gettext-msvc directory.
   You can use 7-Zip (http://www.7-zip.org/) to extract .tar.gz archives.

   The directory structure should then look like this:

   gettext-msvc
   |-- gettext.sln
   |-- gettext-0.19.4
   |   |-- libintl.vcxproj
   |   |-- config.h
   |   |-- libgnuintl.h
   |   |-- gettext-runtime
   |   |   |-- intl
   |   |   |   `-- (lots of source files)
   |   |   `-- (and more...)
   |   `-- (and more...)
   `-- libiconv-1.14
       |-- libiconv.vcxproj
       |-- config.h
       |-- iconv.h
       |-- localcharset.h
       |-- src
       |   |-- iconv.c
       |   `-- (and more...)
       `-- (and more...)

4. Open gettext.sln in Visual Studio 2013.

5. Select a configuration (Release or Debug) and a platform (Win32 or x64)
   and click BUILD -> Build Solution.

Once this is done, the .dll and .lib files are in one of the following
directories (depending on the chosen configuration and platform):

     gettext-msvc/Release-Win32
     gettext-msvc/Release-x64
     gettext-msvc/Debug-Win32
     gettext-msvc/Debug-x64


Acknowledgements
================

A lot of this is based on the solution files provided at

    https://github.com/winlibs/gettext
    https://github.com/winlibs/libiconv

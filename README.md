# libusb-1.0.22

The ubiquity of make means that a makefile is almost the only viable way to distribute automatic build rules for software, but one quickly runs into its numerous limitations. Its lack of support for automatic dependency tracking, recursive builds in subdirectories, reliable timestamps (e.g., for network file systems), and so on, mean that developers must painfully (and often incorrectly) reinvent the wheel for each project. Portability is non-trivial, thanks to the quirks of make on many systems. On top of all this is the manual labor required to implement the many standard targets that users have come to expect (make install, make distclean, make uninstall, etc.). Since you are, of course, using Autoconf, you also have to insert repetitive code in your Makefile.in to recognize @CC@, @CFLAGS@, and other substitutions provided by configure. Into this mess steps Automake. Automake allows you to specify your build needs in a Makefile.am file with a vastly simpler and more powerful syntax than that of a plain makefile, and then generates a portable Makefile.in for use with Autoconf. For example, the Makefile.am to build and install a simple “Hello world” program might look like:

     bin_PROGRAMS = hello
     hello_SOURCES = hello.c
     
The resulting Makefile.in (~400 lines) automatically supports all the standard targets, the substitutions provided by Autoconf, automatic dependency tracking, VPATH building, and so on. make builds the hello program, and make install installs it in /usr/local/bin (or whatever prefix was given to configure, if not /usr/local).

The benefits of Automake increase for larger packages (especially ones with subdirectories), but even for small programs the added convenience and portability can be substantial. And that's not all...

autoreconf --install --force

automake

make

sudo make install

Some influential environment variables:

  CC          C compiler command
  
  CFLAGS      C compiler flags
  
  LDFLAGS     linker flags, e.g. -L<lib dir> if you have libraries in a
              nonstandard directory <lib dir>
     
  LIBS        libraries to pass to the linker, e.g. -l<library>
     
  CPPFLAGS    (Objective) C/C++ preprocessor flags, e.g. -I<include dir> if
              you have headers in a nonstandard directory <include dir
                                                                   
  CXX         C++ compiler command
  
  CXXFLAGS    C++ compiler flags
  
  LT_SYS_LIBRARY_PATH
              User-defined run-time library search path.
              
  CPP         C preprocessor
  
  CXXCPP      C++ preprocessor

# Installation directories:

  --prefix=PREFIX         install architecture-independent files in PREFIX
                          [/usr/local]
                          
  --exec-prefix=EPREFIX   install architecture-dependent files in EPREFIX
                          [PREFIX]

By default, `make install' will install all the files in
`/usr/local/bin', `/usr/local/lib' etc.

You can specify
an installation prefix other than `/usr/local' using `--prefix',
for instance `--prefix=$HOME'.

# Fine tuning of the installation directories:

  --bindir=DIR            user executables [EPREFIX/bin]
  
  --sbindir=DIR           system admin executables [EPREFIX/sbin]
  
  --libexecdir=DIR        program executables [EPREFIX/libexec]
  
  --sysconfdir=DIR        read-only single-machine data [PREFIX/etc]
  
  --sharedstatedir=DIR    modifiable architecture-independent data [PREFIX/com]
  
  --localstatedir=DIR     modifiable single-machine data [PREFIX/var]
  
  --runstatedir=DIR       modifiable per-process data [LOCALSTATEDIR/run]
  
  --libdir=DIR            object code libraries [EPREFIX/lib]
  
  --includedir=DIR        C header files [PREFIX/include]
  
  --oldincludedir=DIR     C header files for non-gcc [/usr/include]
  
  --datarootdir=DIR       read-only arch.-independent data root [PREFIX/share]
  
  --datadir=DIR           read-only architecture-independent data [DATAROOTDIR]
  
  --infodir=DIR           info documentation [DATAROOTDIR/info]
  
  --localedir=DIR         locale-dependent data [DATAROOTDIR/locale]
  
  --mandir=DIR            man documentation [DATAROOTDIR/man]
  
  --docdir=DIR            documentation root [DATAROOTDIR/doc/libusb]
  
  --htmldir=DIR           html documentation [DOCDIR]
  
  --dvidir=DIR            dvi documentation [DOCDIR]
  
  --pdfdir=DIR            pdf documentation [DOCDIR]
  
  --psdir=DIR             ps documentation [DOCDIR]


script for configure and then a correct libusb-1.0.so file is generated whose architecture was for arm(raspberry pi3).



./configure CC=/home/yasir/Development/crosscompile/tools/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian-x64/bin/arm-linux-gnueabihf-gcc  --host=arm-linux --enable-udev=no --enable-shared  --prefix=/usr/local/libusb-rpi



./configure CC=/opt/reach/1.6/sysroots/i686-reachsdk-linux/usr/bin/arm-reach-linux-gnueabi/arm-reach-linux-gnueabi-gcc --host=arm-linux --enable-udev=yes -enable-shared --prefix=/usr/local/libusb 


./configure CC=/opt/reach/2.4.4-1/sysroots/x86_64-reachsdk-linux/usr/bin/arm-reach-linux-gnueabi/arm-reach-linux-gnueabi-g++
host=arm-linux --enable-udev=yes --prefix=/usr/local/libusb

.. include:: replace.txt
.. highlight:: bash

Quick Start
-----------

This chapter summarizes the |ns3| Linux installation process for users
comfortable trying a quick start.  More details on all aspects of Linux
installation are provided in the Overview section, followed by 
distribution-specific guides (Ubuntu, Fedora, Red Hat/CentOS).

Overview
********

|ns3| is built as a system of software libraries that work together.
User programs can be written that links with (or imports from) these
libraries.  User programs are written in either the C++ or Python 
programming languages.

Unlike many Linux libraries, typically installed as binaries with a
Linux package manager, |ns3| focuses on source releases, because most
users end up editing the |ns3| source code.  Source releases can be
built with a C++ compiler (gcc and clang are both supported for Linux).
Usually everything is self-contained in the user's home file system,
and the |ns3| build framework (Waf) also allows running of programs.

Prerequisites
*************

Minimal prerequisites are Python > 2.7.10 and a g++ or clang++ compiler.
Usually, Python is already installed on the system, although g++ may not
be by default.  Ensure that g++ is installed on your system
(type ``g++ --version`` and ensure that the version is >= 4.9).

Either Python2 (2.7) or Python3 (> 3.4) may be used (type ``python -V`` to check).

The core of |ns3| only requires g++ and Python, but some extensions of |ns3|
rely on more libraries.  Use these commands to install a fuller set of
dependencies for a more complete |ns3| build.  If you don't see your
distribution or want to read more about these, read later chapters of this
guide.

* Ubuntu 18.04/Mint 19:

::

  sudo apt-get install ...

* Fedora 29:

::

  sudo dnf install ...

* Red Hat/CentOS 7:

::

  sudo yum install ...

Download
********

There are two main options:

1. Download a release tarball.  This will unpack to a directory such as
``ns-3-allinone``:

::

  $ wget https://www.nsnam.org/releases/ns-allinone-3.29.tar.bz2
  $ tar xfj ns-allinone-3.29.tar.bz2
  $ cd ns-allinone-3.29

2. Clone a repository.  The ``ns-3-allinone`` can be cloned, as well as
``ns-3-dev`` by itself (for work without Python bindings):

::

  $ git clone https://github.com/nsnam/ns-3-dev-git

Build
*****

If you have downloaded ns-3-allinone, run './build.py' to set up the
python bindings generator (pybindgen) and network animator (Netanim):

::

  $ ./build.py

Then change into the ns-3 directory:

:: 

  $ cd ns-3.29

Then build by configuring the system using the Waf build system, and then
compiling:

::

  $ ./waf configure --enable-examples --enable-tests
  $ ./waf build

You should see some output such as below, if successful:

::

  'build' finished successfully (44.159s)
  
  Modules built:
  antenna                   aodv                      applications              
  bridge                    buildings                 config-store              
  core                      csma                      csma-layout               
  dsdv                      dsr                       energy                    
  fd-net-device             flow-monitor              internet                  
  internet-apps             lr-wpan                   lte                       
  mesh                      mobility                  mpi                       
  netanim (no Python)       network                   nix-vector-routing        
  olsr                      point-to-point            point-to-point-layout     
  propagation               sixlowpan                 spectrum                  
  stats                     tap-bridge                test (no Python)          
  topology-read             traffic-control           uan                       
  virtual-net-device        visualizer                wave                      
  wifi                      wimax                     
  
  Modules not built (see ns-3 tutorial for explanation):
  brite                     click                     openflow   
  
  
These programs (the first tutorial program first.cc, and the regression test suite) should also successfully run:

::

  $ ./waf --run 'first'
  $ ./test.py

Summary (ns-3-release)
**********************

Ensure that you have prerequisites you want, download ns-3 from a web browser
or wget into a workspace on your local filesystem, then:

::

  $ tar xjf ns-allinone-3.29.tar.bz2
  $ cd ns-allinone-3.29
  $ ./build.py
  $ cd ns-3.29
  $ ./waf configure --enable-examples --enable-tests
  $ ./waf build

and start using |ns3|.

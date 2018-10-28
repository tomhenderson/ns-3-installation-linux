.. include:: replace.txt

Ubuntu Linux
------------

This chapter describes installation steps specific to Ubuntu Linux and its
derivatives (e.g. Linux Mint).

Consider to put the table here relating Ubuntu releases to ns-3 releases.

Ubuntu 18.04 package prerequisites
**********************************

The following instructions are relevant to ns-3.29 release and Ubuntu 18.04.


* **minimal requirements for C++ (release):**  This is the minimal set of packages needed to run ns-3 C++ programs from a released tarball.

::

  sudo apt-get install gcc g++ python

* **minimal requirements for Python (release):** This is the minimal set of packages needed to run ns-3 C++ and also Python programs from a released tarball.

:: 

  sudo apt-get install gcc g++ python python-dev

* **minimal requirements for Python (development):** For use of ns-3-allinone repository (cloned from Mercurial), additional packages are needed to fetch and successfully install pybindgen:

:: 

  sudo apt-get install mercurial python-setuptools git

* **Netanim animator:**  qt5 development tools are needed for Netanim animator; qt4 will also work but we have migrated to qt5

:: 

  sudo apt-get install qt5-default

* Support for ns-3-pyviz visualizer (requires GTK+ version 3):

::

  sudo apt-get install gir1.2-goocanvas-2.0 python-gi python-gi-cairo python-pygraphviz python3-gi python3-gi-cairo python3-pygraphviz gir1.2-gtk-3.0 ipython ipython3  

**Note:** For ns-3.28 and earlier, PyViz is based on GTK+ 2, GooCanvas, and GraphViz:

:: 

  sudo apt-get install python-pygraphviz python-kiwi python-pygoocanvas libgoocanvas-dev ipython

* Support for MPI-based distributed emulation

::

  sudo apt-get install openmpi-bin openmpi-common openmpi-doc libopenmpi-dev

* Support for bake build tool:

::

  sudo apt-get install autoconf cvs bzr unrar

* Debugging:

::

  sudo apt-get install gdb valgrind 

* Support for utils/check-style.py code style check program

::

  sudo apt-get install uncrustify

* Doxygen and related inline documentation:

::

  sudo apt-get install doxygen graphviz imagemagick texlive texlive-extra-utils texlive-latex-extra texlive-font-utils texlive-lang-portuguese dvipng

* The ns-3 manual and tutorial are written in reStructuredText for Sphinx (doc/tutorial, doc/manual, doc/models), and figures typically in dia (also needs the texlive packages above):

::

  sudo apt-get install python-sphinx dia 

**Note:** Sphinx version >= 1.12 required for ns-3.15.  To check your version, type "sphinx-build".  To fetch this package alone, outside of the Ubuntu package system, try "sudo easy_install -U Sphinx".

* GNU Scientific Library (GSL) support for more accurate WiFi error models

::
  
  sudo apt-get install gsl-bin libgsl2 libgsl-dev

* The Network Simulation Cradle (nsc) requires the flex lexical analyzer and bison parser generator:

::

  sudo apt-get install flex bison libfl-dev

* To read pcap packet traces

::
 
  sudo apt-get install tcpdump

* Database support for statistics framework

::

  sudo apt-get install sqlite sqlite3 libsqlite3-dev

* Xml-based version of the config store (requires libxml2 >= version 2.7)

::

  sudo apt-get install libxml2 libxml2-dev

* Support for API scanning (generating modified Python bindings):

::

  sudo apt-get install cmake libc6-dev libc6-dev-i386 libclang-dev llvm-dev automake
  pip install cxxfilt

and you will want to install castxml and pygccxml as per the instructions for python bindings (or through the ''bake'' build tool as described in the tutorial).  The 'castxml' package provided by Ubuntu 18.04 and earlier is not recommended; a source build (coordinated via bake) is recommended.

* A GTK-based configuration system

::

  sudo apt-get install libgtk2.0-0 libgtk2.0-dev

* To experiment with virtual machines and ns-3

::

  sudo apt-get install vtun lxc

* Support for openflow module (requires some boost libraries)

::

  sudo apt-get install libboost-signals-dev libboost-filesystem-dev

Other Ubuntu releases
*********************

Describe any differences between Ubuntu 18.04 base instructions and other
Ubuntu variants.

Ubuntu 16.04
++++++++++++

This also pertains to Linux Mint 18.

**Note:** For API scanning, Ubuntu 16.04 and systems based on it (e.g. Linux Mint 18) default to an old version of llvm (3.8).   Users of Ubuntu 16.04 will want to explicitly install a newer version by specifying 'libclang-6.0-dev' and 'llvm-6.0-dev'.


Ubuntu 14.04
++++++++++++

**Note:** Ubuntu 14.04 LTS release requires upgrade to gcc-4.9 from default gcc-4.8.  More recent Ubuntu versions are OK.  The instructions at this link: http://askubuntu.com/questions/466651/how-do-i-use-the-latest-gcc-on-ubuntu?answertab=votes#tab-top have been found to work.

Ubuntu 12.04
++++++++++++

Current |ns3| releases are no longer supported.  Older |ns3| releases
(up to ns-3.xx) were supported for Ubuntu 10.

Troubleshooting
***************

Summarize any caveats or issues with Ubuntu.



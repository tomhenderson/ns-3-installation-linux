.. include:: replace.txt

Overview
---------

This is a placeholder chapter to go into more detail about installation
process in general.  This is to be followed up by distribution-specific
guides for Ubuntu, Fedora, Red Hat/CentOS (and others).

Base and optional components
****************************

Some |ns3| modules only require g++:  core, network, internet.

Many |ns3| modules also require supplemental libraries.

* pyviz
* NetAnim
* MPI
* BRITE
* ns-3-dce
* wifi (GSL)

Go through each one of these optional dependencies and explain general Linux
installation steps and caveats.

Compatibility between ns-3 versions and system components
*********************************************************

Describe how ns-3 versions may have different interactions with the libraries
found on various Linux distributions.  This could be place for a table that
lists, for instance, which compiler version is tested with which release.

Describe what to do to disable Werror.

Debian packages
***************

Summarize how to use these (packages put together by Martin Quinson).

Summarize the benefits/drawbacks of these binary packages.




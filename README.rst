openwrt-bash-completion
=======================

Bash completion script for OpenWrt make targets.

The purpose of this script is to save you from some typing when working with
OpenWrt buildroot. Default completion for GNU Make distributed with Bash
Completion is unable to discover all the targets that can be built by the
buildroot. This script tries to improve this situation by searching for
Makefiles in the buildroot and translating their paths to make targets. It can
also parse the database of make targets and offer completion based on this
output (see Mode Selection below).


Installation
------------

To install this bash completion script it should be sufficient on most systems
that have Bash Completion installed to copy ``openwrt_make`` to
``/etc/bash_completion.d/`` or to add it to your ``.bashrc`` file.


Mode Selection
--------------

openwrt-bash-completion can work in two modes. Default mode is completion
based on Makefile discovery, where relevant parts of the buildroot are searched
for existing Makefiles and their paths are translated into names of make
targets. This mode is faster and does not need to run the make command. However
not all targets can be discovered in this mode - mainly host-build targets and
some subtargets of toolchain.

Second mode of operation is completion based on output of ``make printdb``
command. This can be enabled by setting ``OPENWRT_COMPL_USE_PRINTDB=1`` in the
current Bash session or in your ``.bashrc`` file. In this mode, most (if not
all) targets can be found, however it's not as fast as the default target
discovery. This problem is solved by caching of the parsed output to
``OPENWRT_COMPL_CACHE`` variable if ``OPENWRT_COMPL_CACHE_PRINTDB`` is set to
``1`` (default value). Please note that this cache must be cleared if the
package definitions changed (some packages or target definitions were added).
This can be achieved either by restarting of the Bash session or simply by
running ``OPENWRT_COMPL_CACHE=``.


License & Contributing
----------------------

This script is released under the MIT license. Any contributions or suggestions
for improvement are appreciated.

openwrt-bash-completion
=======================

Bash completion script for OpenWrt make targets.

The purpose of this script is to save you from some typing when working with
OpenWrt buildroot. Default completion for GNU Make distributed with Bash
Completion is unable to discover all the targets that can be built by the
buildroot. This script tries to improve this situation by searching for
Makefiles in the buildroot and translating their paths to make targets.


Installation
------------

To install this bash completion script it should be sufficient on most
systems that have Bash Completion installed to copy openwrt_make to
/etc/bash_completion.d/ or to add it to your .bashrc file.


License & Contributing
----------------------

This script is released under the MIT license. Any contributions or suggestions
for improvement are appreciated.

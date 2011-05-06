`syncto` and `syncfrom`
=======================

Syncs files between your home computers using rsync.  This is merely
a convenient wrapper around rsync commands, rather than a sync utility by
itself.

Usage
=====

To copy local files from the given path spec to another computer, overwriting
everything that's there:

    nvie@MacBook$ syncto -vu vincent iMac.local Projects/syncfrom

To pull changes from the other computer, overwriting your local copy:

    nvie@MacBook$ syncfrom -vu vincent iMac.local Projects/syncfrom

Both `syncto` and `syncfrom` will keep the names of the directories used
identical on both systems.  It is not possible to change the directory names
when using these wrappers.  If you want that kind of control, use rsync
directly.  If you use relative directories, they will be relative to the
`$HOME` directory for the local and remote users.

Installation
============

Put these files somewhere on your `$PATH`.

Disclaimer
==========
I built this purely to scratch my own itch.  It is not guaranteed to work on
your system.

What users are saying about it
==============================
"I don't sync so."

`syncto` and `syncfrom`
=======================

Syncs files between your home computers using rsync.  This is merely
a convenient wrapper around rsync commands, rather than a sync utility by
itself.

Usage
=====

To copy local files from the given path spec to another computer, overwriting
everything that's there:

    nvie@MacBook$ syncto -v vincent@iMac.local Projects/syncfrom

To pull changes from the other computer, overwriting your local copy:

    nvie@MacBook$ syncfrom -v vincent@iMac.local Projects/syncfrom

Both `syncto` and `syncfrom` will keep the names of the directories used
identical on both systems.  It is not possible to change the directory names
when using these wrappers.  If you want that kind of control, use rsync
directly.

If your path spec is a directory inside your home directory, the remote part of
the rsync command is automatically converted to the user's home directory on
the remote end, too, *even if the username is different*.

You can spec your sync path using either of the following notations:

    nvie@MacBook ~/Projects/syncfrom$ syncfrom -v vincent@iMac.local .
    nvie@MacBook ~$ syncfrom -v vincent@iMac.local Projects/syncfrom
    nvie@MacBook /tmp$ syncfrom -v vincent@iMac.local /Users/nvie/Projects/syncfrom

Each of these commands has exactly *the same* effect---they will push all files
inside the (local) directory `/Users/nvie/Projects/syncfrom` to the remote
system's `/Users/vincent/Projects/syncfrom` directory.

`syncto` and `syncfrom` currently take only one path spec to sync.

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

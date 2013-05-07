# osx-fdisk

## Overview

The [fdisk](https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man8/fdisk.8.html) utility included in Mac OS X has the ability to dump the partition table of a block device or file and reuse it with the -d / -r parameters. Unfortunately, parsing the dump is broken to the point of being unusable.

This patched version of fdisk is based on the [sources for the package diskdev_cmds](http://www.opensource.apple.com/source/diskdev_cmds/diskdev_cmds-557.3/) included with Mac OS X 10.8.3. An Xcode project definition is included. It fixes the following bugs:

    * correctly parses partition end information into the right variables
    * correctly calculates the partition offsets of (chained) extended partitions
    * correctly makes the parsed geometry settings take precedence over the parsed start/length fields and avoids LBA correction

**Disclaimer:** this work comes without any warranty, in fact it could easily wipe your data. Use it with caution!

## License

As required, this work is released under the [Apple Public Source License](http://www.opensource.apple.com/license/apsl/).

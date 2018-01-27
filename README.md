## Description

This project makes it possible to automatically prefix filenames with the creation date of the file on Mac OSX. For example: `myfile.txt` becomes `2018-01-05 myfile.txt`.

It's made up of a Ruby script (`bin/datestamp`) which is called from an Automator workflow which can, in turn, be triggered by a keyboard shortcut.

## Setup

### Link to Ruby script from a location in your PATH

For example:

    $ ln -s ~/Code/floehopper/datestamp/bin/datestamp ~/bin/datestamp

### Copy workflow into Services directory

For example:

    $ cp -R Datestamp.workflow ~/Library/Services/

### Install workflow as a service

For example:

    $ open ~/Library/Services/Datestamp.workflow

And follow the GUI instructions.

### Add Finder keyboard shortcut for Datestamp service

The following adds the keyboard shortcut ⌘d to run the Datestamp service:

    $ defaults write com.apple.finder NSUserKeyEquivalents '{ Datestamp = "@d"; }'

### Dependencies

The Ruby script currently depends on Ruby v2.5.0 provided by [`rbenv`][1], because [`Pathname#birthtime`][2] is a recent addition to Ruby.

The whole project has only been tested on Mac OSX Sierra (v10.12.6).

### License

You may use, copy and redistribute this library under the MIT license.

© Copyright James Mead 2018

[1]: https://github.com/rbenv/rbenv
[2]: https://ruby-doc.org/stdlib-2.5.0/libdoc/pathname/rdoc/Pathname.html#method-i-birthtime

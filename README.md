![Build][badge-ci]


### LibYAML - A C library for parsing and emitting YAML.

This is a _private_ dupplicate of the _official_ [LibYAML project]. It was initiated at a time when the GitHub repository
appeared to little to no activity. As the AIT framework intensively relies on this library we decided to create this repository
while continuously monitoring the upstream master repository.


#### How this repository was setup

To build and install the library, run:

    $ ./configure
    $ make
    # make install

Required packages:

- gcc
- libtool
- make

If you checked the source code from the Git repository, run

    $ ./bootstrap
    $ ./configure
    $ make
    # make install

Required packages:

- autoconf
- libtool
- make


Discuss LibYAML with the maintainers in IRC #libyaml irc.freenode.net.

You may also use the [YAML-Core mailing
list](http://lists.sourceforge.net/lists/listinfo/yaml-core).

Submit bug reports and feature requests to the [LibYAML bug
tracker](https://github.com/yaml/libyaml/issues/new).

This project was developed for Python Software Foundation as a part of Google
Summer of Code under the mentorship of Clark Evans.

The _libYAML_ library was written by Kirill Simonov <xi@resolvent.net> and is currently maintained by the YAML community. Our
local copy is essentially the original code with minor updates.

Please don't add

LibYAML is released under the MIT license.
See the file LICENSE for more details.

<!-- # Bookmarks -->

  [libyaml]: https://github.com/yaml/libyaml
  [badge-ci]: https://github.com/ISLEcode/ait-libyaml/workflows/C/C++%20CI/badge.svg

<!-- vim: set digraph nospell :-->

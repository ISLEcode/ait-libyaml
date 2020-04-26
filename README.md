![CentOS][ci-centos] ![Ubuntu][ci-ubuntu] ![MacOS][ci-macos]

### LibYAML - A C library for parsing and emitting YAML.

The _libYAML_ library was written by Kirill Simonov <xi@resolvent.net> and is currently maintained by the YAML community. It was
originally developed for _Python Software Foundation_ as a part of _Google Summer of Code_ under the mentorship of _Clark Evans_.

**Important.** This is a fork of the _official_ [LibYAML project][libyaml]. It was initiated at a time when the original project
appeared to have little to no activity. As the AIT framework intensively relies on this library we decided to do a bare bones
fork which could evolve by its own while continuously monitoring the upstream master repository
(see "_How this repository was setup_" below).

#### Build from source

1.  Dependencies:

    -   GNU AutoTools
    -   GNU Gcc
    -   GNU Libtool

1.  Howto build from source code

    ``` .sh
    ./bootstrap
    ./configure
    make
    make install
    ```

#### Issues & discussion boards

-   Issues: [AIT related][aityaml-issues] or specific to [libyaml][libyaml-issues].
-   IRC: `#libyaml` @ _irc.freenode.net_.
-   Mailing list: [YAML-Core][yaml-core]

#### How this repository was setup

The repositories:

-   [yaml/libyaml][libyaml] is the _upstream_ repository we want to monitor
-   [ISLEcode/ait-libyaml][aityaml] is the _origin_ repository where we manage _our_ copy of the C library

The working instructions:

1.  Create empty GitHub repository (_ISLEcode/ait-libyaml_).

1.  Clone the _upstream_ `libyaml` Git repository we want to monitor.

    ``` {.sh}
    git clone https://github.com/yaml/libyaml libyaml
    cd libyaml
    ```

1.  Remove the _origin_ remote and add an _upstream_ remote.

    ``` {.sh}
    git remote remove origin
    git remote add upstream https://github.com/yaml/libyaml
    ```

1.  Bind the cloned repository to our GitHub repository

    ``` {.sh}
    git remote add origin https://github.com/ISLEcode/ait-libyaml
    git push --set-upstream origin master
    ```

1.  Create a branch that we will use to sink with the _upstream_ remote.

    ``` {.sh}
    git branch libyaml/master
    git push --set-upstream origin master
    ```

1.  Now each time we want to sync with the _upstream remote_, all we need to do is:
    ``` {.sh}
    git checkout libyaml/master
    git pull upstream master
    ```

See also:

-   [Learn Git branching][git-branching]
-   [A hacker's guide to Git][git-hacker]

<!-- # Bookmarks -->

  [aityaml-issues]: https://github.com/ISLEcode/ait-libyaml/issues
  [aityaml]: https://github.com/ISLEcode/ait-libyaml
  [ci-centos]: https://github.com/ISLEcode/ait-libyaml/workflows/CentOS/badge.svg
  [ci-macos]: https://github.com/ISLEcode/ait-libyaml/workflows/macOS/badge.svg
  [ci-ubuntu]: https://github.com/ISLEcode/ait-libyaml/workflows/Ubuntu/badge.svg
  [git-branching]: https://pcottle.github.io/learnGitBranching/
  [git-hacker]: https://wildlyinaccurate.com/a-hackers-guide-to-git
  [libyaml-issues]: https://github.com/yaml/libyaml/issues
  [libyaml]: https://github.com/yaml/libyaml
  [yaml-core]: http://lists.sourceforge.net/lists/listinfo/yaml-core

<!-- vim: set digraph nospell :-->

![CentOS][ci-centos] ![Ubuntu][ci-ubuntu] ![MacOS][ci-macos]

### LibYAML - A C library for parsing and emitting YAML.

The _libYAML_ library was written by Kirill Simonov <xi@resolvent.net> and is currently maintained by the YAML community. It was
originally developed for _Python Software Foundation_ as a part of _Google Summer of Code_ under the mentorship of _Clark Evans_.
Our local copy is essentially the original code with minor updates. 

**Important.** This is a _private_ dupplicate of the _official_ [LibYAML project]. It was initiated at a time when the GitHub
repository appeared to little to no activity. As the AIT framework intensively relies on this library we decided to create this
repository while continuously monitoring the upstream master repository (see [how this repository was setup][] below.

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



Open Source projects have varying life cycles; many interesting projects have not been updated in year. In some cases it is
important to maintain a copy (and not a fork) of the project locally while monitoring changes made to the _upstream_ project.

What I describe here is how I perform such setups when the project we want to monitor is maintained as a git repository. As a
practica example we are going to examine a real world example: the [libyaml] C library. This is an essential component of the
AIT framework and the library has had little to no activity during the last years[^1].

Our setup is as follows:

-   [yaml/libyaml] is the upstream repository we want to monitor
-   [ISLEcode/ait-libyaml] is the _origin_ repository where we manage _our_ copy of the C library



Though I have seen activity and new releases recently. Which exemplifies why we want to keep monitoring the originating
repository.

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

[Learn Git branching]: https://pcottle.github.io/learnGitBranching/
[A hacker's guide to Git]: https://wildlyinaccurate.com/a-hackers-guide-to-git

<!-- # Bookmarks -->

  [libyaml]: https://github.com/yaml/libyaml
  [libyaml-issues]: https://github.com/yaml/libyaml/issues
  [aityaml-issues]: https://github.com/ISLEcode/ait-libyaml/issues
  [ci-ubuntu]: https://github.com/ISLEcode/ait-libyaml/workflows/Ubuntu/badge.svg
  [ci-centos]: https://github.com/ISLEcode/ait-libyaml/workflows/CentOS/badge.svg
  [ci-macos]: https://github.com/ISLEcode/ait-libyaml/workflows/macOS/badge.svg
  [yaml-core]: http://lists.sourceforge.net/lists/listinfo/yaml-core

<!-- vim: set digraph nospell :-->

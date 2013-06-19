sticky.sh
---------

`sticky` is a bash utility to make something like "sticky notes" when working at
the terminal.

Usage
-----

Create notes

```bash
$ sticky add "This is a note"
```

List current notes

```bash
$ sticky ls
1. 2013-06-19 1206 ~
This is a note
```

In the case of the `add` command, you can skip the command name and `add` is
assumed.  You also don't have to put the contents of the note into quotation
marks -- `sticky` takes all the input from `$@` and puts it into the note.  Of
course, if you skip the quotes bash will expand whatever you pass in, but this
can be useful sometimes.

```bash
$ sticky Another note
$ sticky Bash related files are: *.bash*
$ sticky ls
1. 2013-06-19 1206 ~
This is a note
2. 2013-06-19 1215 ~
Another note
3. 2013-06-19 1216 ~
Bash-related files are .bash_completion.d .bash_history .bash_logout .bash_profile .bashrc
```

Remove a note

```bash
$ sticky rm 2
$ sticky ls
1. 2013-06-19 1206 ~
This is a note
3. 2013-06-19 1216 ~
Bash-related files are .bash_completion.d .bash_history .bash_logout .bash_profile .bashrc
```

Contributing
------------

Please do!  This script is intended to be kept pretty basic, but there are some
obvious improvements that could be made:

* Files can take any name, but there is currently no interface to give them a
  name other than the default incrementing number.
* Similarly, there is no user interface for renaming files (though if you just
  rename them manually in `~/.sticky` it should "just work"

If you do want to contribute, just fork and pull request as usual.  I like clean
commits without spurious whitespace and the like, and decent commit messages
(but then who doesn't?), so please do those things.

Licence
-------

Copyright (c) Daniel P. Wright.

This software is released under the Simplified BSD Licence.  See LICENCE.md for
further details.

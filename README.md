# insit
Installer for many shell programs from terminalforlife.

**MASTER** - _Hopefully stable branch._\
**DEV** - _Development Branch (latest changes)_

INTRODUCTION
------------

Just download and install this handy-dandy installer in order to run it and install all of the TFL programs, scripts, tools, utilities, or whatever else (mostly) is up for grabs here.

This was born from the clumsy "installit" - original installer I used. I wanted something easier and more featureful for both myself and other users. Updating, installing, and uninstalling is now much simpler. Don't worry, the installer can, per your request, update itself as well.

HOW TO USE
----------

Execute this simple one-liner to download and install insit:

```bash
sudo wget -q https://raw.githubusercontent.com/terminalforlife/insit/master/insit -O /usr/bin/insit && sudo chmod u+x /usr/bin/insit
```

EXAMPLE
-------

Now that you've done that, all that's left is to load up insit to peruse the catalogue of my work at your own leisure. Here is its `--help` output, as of 2017-12-17:

```
$ insit --help
            INSIT (17th December 2017)
            Written by terminalforlife (terminalforlife@yahoo.com)

            Installer for many shell programs from terminalforlife.

SYNTAX:     insit [OPTS] WHAT1 WHAT2 WHAT3 . . .

OPTS:       --help|-h|-?            - Displays this help information.
            --debug                 - Enables the built-in bash debugging.
            --quiet|-q              - Runs in quiet mode. Errors still output.
            --update|-U             - Replace and update existing files.
            --uninstall|-u          - Uninstall files installed here.
            --available|-A          - Output all available programs.
            --branch|-B NAME        - Where NAME is the branch to use.
            --self-update|-S        - Update insit to the latest stable version.

NOTE:       Where WHAT is the program(s) to install.

WARNING:    Uninstalling with this program is permanent!

SITE:       https://github.com/terminalforlife
```

An example installation of a program already installed:

```bash
$ sudo insit medlog
[L0107] ERROR: File already exists: /usr/bin/medlog
```

Now to update it, since it's already installed:

```bash
$ sudo insit -U medlog
File '/usr/bin/medlog' downloaded and updated.
File '/usr/bin/medlog' ownership re-set.
File '/usr/bin/medlog' mode re-set.
```

To install the same program if it weren't already found:

```bash
$ sudo insit medlog
File '/usr/bin/medlog' downloaded.
File '/usr/bin/medlog' ownership set.
File '/usr/bin/medlog' mode set.
```

Uninstalling a program is easy too:

```bash
$ sudo insit -u medlog
File '/usr/bin/medlog' removed.
```

What if you want to update the installer itself? Easy:

```bash
$ sudo insit -S
File '/usr/bin/insit' downloaded and updated.
File '/usr/bin/insit' ownership re-set.
File '/usr/bin/insit' mode re-set.
Successful insit update.
```

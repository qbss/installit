# insit
Installer for many shell programs from terminalforlife.

**MASTER** - _Hopefully stable branch._\
**DEV** - _Development Branch (latest changes)_

INTRODUCTION
------------

Just download and install this handy-dandy installer in order to run it and install all of the TFL programs, scripts, tools, utilities, or whatever else (mostly) is up for grabs here. Don't worry, the installer can, per your request, update itself as well.

As of 29th January 2018, bash completion is now fully supported and working in insit. This is also gradually coming to other TFL programs, such as apt-undo-install, so watch this space!

HOW TO GET THIS INSTALLER
-------------------------

Execute the following one-liner to download and install insit:

```bash
sudo wget -q https://raw.githubusercontent.com/terminalforlife/installit/master/insit -O /usr/bin/insit && sudo chmod 755 /usr/bin/insit
```

Then, if you have bash completion installed (which most do), then execute this command as well:

```bash
sudo wget -q https://raw.githubusercontent.com/terminalforlife/installit/master/completion -o /usr/share/bash-completion/completions/insit && sudo chmod 644 /usr/share/bash-completion/completions/insit
```

Or, if you'd prefer, you could clone or download (via the green button) this installit repository, then, once you've got access to the insit program, run the following from within the very same directory:

```bash
sudo insit -S
```

While that command is ordinarily for updating a pre-existing installation of insit, it'll also serve to install it -- bonus.

EXAMPLE
-------

Now that you've done that, all that's left is to load up insit to peruse the catalogue of my work at your own leisure. Here is its `--help` output, as of 2017-12-17:

```
$ insit --help
            INSIT (29th January 2018)
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
            --custom|-C             - Execute your own FILE function line.

NOTE:       Where WHAT is the program(s) to install.

            The argument positions for the FILE function:

              1: Name of the repository, per the URL.
              2: Name of the file, per the URL, to download.
              3: Desired name of the file to be Downloaded.
              4: The permissions (mode), such as 755 or 644.
              5: The file's owner and group, such as 0 or $USER.

EXAMPLE:    sudo insit -B dev -U -C miscellaneous mfw /usr/bin/mfw 755 0
            sudo insit -U notify-upgrade lspkg lsbins apt-undo-install
            sudo insit --quiet --uninstall bl medlog wcdl clean-locales

WARNING:    Uninstalling with this program is permanent!

            Using the --update|-U flags will overwrite existing files, so, if an
            executable just so happens to have the same name, take care not to
            replace it by mistake!

            All programs, scripts, and other files from the below SITE will contain
            the comment header you see within this file, so grepping for the E-Mail
            address or GitHub URL below would be a good way to check.

SITE:       https://github.com/terminalforlife
```

An example installation of a program already installed:

```bash
$ sudo insit medlog
[L0127] ERROR: File already exists: /usr/bin/medlog
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
$ sudo insit --uninstall medlog
File '/usr/bin/medlog' removed.
```

What if you want to update the installer itself? Easy:

```bash
$ sudo insit -S
File '/usr/bin/insit' downloaded and updated.
File '/usr/bin/insit' ownership re-set.
File '/usr/bin/insit' mode re-set.
File '/usr/share/bash-completion/completions/insit' downloaded and updated.
File '/usr/share/bash-completion/completions/insit' ownership re-set.
File '/usr/share/bash-completion/completions/insit' mode re-set.
```

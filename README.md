# insit
Installer for many shell programs from terminalforlife.

**MASTER** - _Hopefully stable branch._\
**DEV** - _Development Branch (latest changes)_

## INTRODUCTION

Just download and install this handy-dandy installer in order to run it and install all of the TFL programs, scripts, tools, utilities, or whatever else (mostly) is up for grabs here. Don't worry, the installer can, per your request, update itself as well.

As of 29th January 2018, bash completion is now fully supported and working in insit. This is also gradually coming to other TFL programs, such as apt-undo-install, lspkg, simplify-ubuntu, and ubuntu-syschk, so watch this space!

## HOW TO GET THIS INSTALLER

Execute the following one-liner to download and install insit:

```bash
wget -q https://github.com/terminalforlife/installit/raw/master/insit && sudo bash insit -S
```

Or, if you'd prefer, you could clone or download (via the green button) this installit repository, then, once you've got access to the insit program, run the following from within the very same directory, to install the latest insit:

```bash
sudo bash insit -S
```

While that command is ordinarily for updating a pre-existing installation of insit, it'll also serve to install it -- bonus.

## EXAMPLE

Now that you've done that, all that's left is to load up insit to peruse the catalogue of my work at your own leisure. Here is its `--help` output, as of 4th March, 2018:

```
$ insit --help
            INSIT (2018-03-06)
            Written by terminalforlife (terminalforlife@yahoo.com)

            Installer for many shell programs from terminalforlife.

SYNTAX:     insit [OPTS] WHAT1 WHAT2 WHAT3 . . .

OPTS:       --help|-h|-?            - Displays this help information.
            --verbose|-V            - Also display the log output.
            --version|-v            - Output only the version datestamp.
            --debug|-D              - Enables the built-in bash debugging.
            --quiet|-q              - Runs in quiet mode. Errors still output.
            --update|-U             - Replace and/or update existing files.
            --uninstall|-u          - Uninstall files installed here.
            --available|-A          - Output all available programs.
            --branch|-B NAME        - Where NAME is the branch to use.
            --self-update|-S        - Update insit to the latest stable version.
            --ignore-root|-I        - Disregard whether you have root access.
            --custom|-C             - Execute your own FILE function line.
            --log|-L                - Log and time-stamp actions to take.

NOTE:       Where WHAT is the program(s) to install.

            The argument positions for the FILE function:

              1: Name of the repository, per the URL.
              2: Name of the file, per the URL, to download.
              3: Desired name of the file to be Downloaded.
              4: The permissions (mode), such as 755 or 644.
              5: The file's owner, such as 0 or $USER.
              6: The file's group, such as 1000.

EXAMPLE:    sudo insit -B dev -U -C miscellaneous mfw /usr/bin/mfw 755 0
            sudo insit -U notify-upgrade lspkg lsbins apt-undo-install
            sudo insit -q --log --uninstall bl medlog wcdl clean-locales

WARNING:    Using the --update|-U flags will overwrite existing files, so, if an
            executable just so happens to have the same name, take care not to
            replace it by mistake!

FILE:       The log file is stored in: /var/log/tfl_insit.log

SITE:       https://github.com/terminalforlife
```

An example installation of a program already installed:

```bash
$ sudo insit apt-undo-install
[L0189] ERROR: File already exists: /usr/bin/apt-undo-install
[L0189] ERROR: File already exists: /usr/share/bash-completion/completions/apt-undo-install
```

Now to update it, since it's already installed:

```bash
$ sudo insit -U apt-undo-install
File '/usr/bin/apt-undo-install' downloaded and updated.
File '/usr/bin/apt-undo-install' ownership re-set.
File '/usr/bin/apt-undo-install' mode re-set.
File '/usr/share/bash-completion/completions/apt-undo-install' downloaded and updated.
File '/usr/share/bash-completion/completions/apt-undo-install' ownership re-set.
File '/usr/share/bash-completion/completions/apt-undo-install' mode re-set.
```

To install the same program if it weren't already found:

```bash
$ sudo insit apt-undo-install
File '/usr/bin/apt-undo-install' downloaded.
File '/usr/bin/apt-undo-install' ownership set.
File '/usr/bin/apt-undo-install' mode set.
File '/usr/share/bash-completion/completions/apt-undo-install' downloaded.
File '/usr/share/bash-completion/completions/apt-undo-install' ownership set.
File '/usr/share/bash-completion/completions/apt-undo-install' mode set.
```

Uninstalling a program is easy too:

```bash
$ sudo insit --uninstall apt-undo-install
This will delete installed files -- continue? y
File '/usr/bin/apt-undo-install' deleted.
File '/usr/share/bash-completion/completions/apt-undo-install' deleted.
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

You'll also get a warning for certain key installations, such as vimconfig:

```bash
$ sudo insit -U vimconfig
WARNING: This will install and replace the following:

  /home/tfl/.vimrc
  /home/tfl/.vim/colors/tfl.vim
  /home/tfl/.vim/plugin/altnums.vim
  /home/tfl/.vim/plugin/autoscroll.vim
  /home/tfl/.vim/plugin/banger.vim
  /home/tfl/.vim/plugin/comtog.vim
  /home/tfl/.vim/plugin/datepaste.vim
  /home/tfl/.vim/plugin/exefile.vim
  /home/tfl/.vim/plugin/headup.vim
  /home/tfl/.vim/plugin/listmode.vim
  /home/tfl/.vim/plugin/moredoc.vim
  /home/tfl/.vim/plugin/mouseon.vim
  /home/tfl/.vim/plugin/noarrows.vim
  /home/tfl/.vim/plugin/sanekeys.vim
  /home/tfl/.vim/plugin/simplyhard.vim
  /home/tfl/.vim/plugin/sudosave.vim
  /home/tfl/.vim/plugin/textwidth.vim
  /home/tfl/.vim/plugin/tflsnips.vim
  /home/tfl/.vim/plugin/togtrans.vim
  /home/tfl/.vim/plugin/virtedit.vim

Enter 'Yes!' if you're sure you wish to continue:
```

At which point you just type 'Yes!' exactly as you see it in the above prompt, then press the Enter key, and away you go! Just, fair warning, be absolutely sure to have **backed up your files** before you give the go-ahead.

You'll probably be glad to know that insit also supports helpful logging via /var/log/tfl_insit.log. The log file is by default not accessible by anyone other than root. Here's an example of what your insit log file will show, if you execute the second example shown above:

```
$ sudo cat /var/log/tfl_insit.log
[2018-03-06_22:25:54]: FILE apt-undo-install completion /usr/share/bash-completion/completions/apt-undo-install 644 0 0
[2018-03-06_22:25:54]: Downloading github.com/terminalforlife/apt-undo-install/master/completion to /usr/share/bash-completion/completions/apt-undo-install
[2018-03-06_22:25:54]: Downloaded github.com/terminalforlife/apt-undo-install/master/completion to /usr/share/bash-completion/completions/apt-undo-install
[2018-03-06_22:25:54]: Setting /usr/share/bash-completion/completions/apt-undo-install to 0 UID and 0 GID
[2018-03-06_22:25:54]: Set /usr/share/bash-completion/completions/apt-undo-install to 0 UID and 0 GID
[2018-03-06_22:25:54]: Setting /usr/share/bash-completion/completions/apt-undo-install to 644 permissions
[2018-03-06_22:25:54]: Set /usr/share/bash-completion/completions/apt-undo-install to 644 permissions
```

Want a list of all of the items available with insit? Be sure to update insit to be sure you're seeing the latest list, but as of now:

```
$ insit -A
apt-undo-install - Undo the last package(s) install executed with apt-get.
autoscrot - Tool to take full screenshots at user-specified intervals using scrot.
backmeup - A simple tool to quickly and easily back up your HOME.
bashconfig - My own bash settings and shell plugins for use by anybody.
bdl - Easily and quickly download a batch of files using wget.
binwatch - Output list of executables found in your PATH
bios-info - Simple tool to show basic BIOS keys and their values.
bl - Much simpler, quicker version of blkid.
capnum - Small tool to notify of NumLock and CapsLock status changes.
catmedia - Concatenate media files originally separated in parts.
clean-locales - Remove some unnecessary non-English localizations.
compconf - The terminalforlife configuration file for compton.
cpufreq - Lightweight Bourne Shell utility to output your CPU frequencies.
dlfallwalls - Download a collection of Autumn/Fall wallpapers.
dlfcmags - Download issues of the Full Circle magazine PDFs.
dlspwalls - Download a collection of steampunk wallpapers.
dl-tuxradar-podcasts - Small shell program to download the TuxRadar podcasts.
dunstconfig - The terminalforlife configuration file for dunst.
dwwdl - Download all of the available DistroWatch Weekly podcasts.
forex - Easily convert various currency rates straight from the terminal.
getip - View your internal and/or external IP address.
getline - Pure Bourne Again Shell way to handle a plain text file.
get-uuid - Grab and copy your file system's UUID with this simple, easy-to-use GUI.
ghipc - Check the validity of IP addresses of GitHub servers.
github-ssh-setup - Simple shell program to create an SSH key pair for GitHub.
homewatch - Output files in HOME which have been modified today.
i3config - My own i3-wm settings and shell plugins for use by anybody.
jotd - Display a Joke of the Day on your terminal.
kernelchk - Small tool to check for a change in kernel version. Ideal for scripts.
lsbins - Simple shell program to list and describe the PATH executables.
lspkg - Quickly and portable-y show, describe, and search installed packages.
mansaver - Save man pages for each applicable command in PATH.
medlog - Need help taking and logging when you've had your medication?
mfw - Notifier for page-one threads on the Newbie Questions Linux Mint forum.
mif - Shell program to filter films by year and whether seen or not.
mkpass - Pure Bourne Again Shell approach to complex password generation.
mplay - Simple script to allow me to quickly load mocp how I like.
nosp - A workaround for the issue in XFCE wherein Smart Placement refuses to go away.
notify-upgrade - Simple upgrade notification utility for Debian- and Ubuntu-based systems.
nxbt - A fork and improvement of the XBT program written by Joe Collins.
pagewatch - Watch a webpage for signs of change by checkings its md5sum.
redshifter - Effective and simple tool to manually adjust the gamma via Redshift.
reviewer - Terminal viewer for Linux Mint's user submitted software reviews.
ripmydvd - Shell program using ffmpeg and mplayer to rip your DVD.
roks - This small program will clear out your system of old kernel versions.
seewttr - Super-simple wrapper-like script to get your weather.
simplify-ubuntu - Small project to lighten standard Ubuntu 16.04.3 LTS installations.
simwea - Display various weather statistics on a terminal.
snotes - Search your programming notes on-the-fly with this simple tool.
tozero - Simple program to display a countdown for a target date.
ubuntu-syschk - Performs various non-root system health checks on Ubuntu and similar.
vimconfig - TFL plugins and more for the Vi-IMproved (VIM) modal text editor.
wcdl - Crawl WallpapersCraft for desktop backgrounds. Includes wcdl tools.
```

I hope you enjoy insit as much as I enjoyed writing it.

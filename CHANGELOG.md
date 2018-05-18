* 2018-05-18

Added tlptog to insit.

* 2018-05-01

Now back from holiday.

When testing Ubuntu 18.04 LTS "Bionic Beaver" (full release) in a virtual machine, an XERR() instance popped up, due to the one-liner method in which insit was initially installed:

```bash
wget -q github.com/terminalforlife/installit/raw/master/insit && sudo bash insit -S; rm ./insit
```

The error was in relation to improper permissions and/or ownership with file:

```
$HOME/.local/share/insit/last
```

This has now _hopefully_ been addressed. Likely the same issue occurred in other setups prior to Ubuntu 18.04, so they too should hopefully be fixed now.

* 2018-04-22

Managed to get in an update before I go on holiday.

Added `REPLACE_PROMPT` functionality, which optimizes the code, making it easier to read and handle, and as an added bonus, saves around 41 lines.

This equals less effort on my part when it comes to adding these prompts which confirm the user is okay with replacing certain files, such as their own `.bashrc` and `.vimrc`, which of course warrant confirmation, as these may be personally modified, prior to the attempted installation.

* 2018-04-14

Migrated `feh_slides` from the i3config repository to `feh-slides` in the miscellaneous repository, now with additional features and room for expansion. This will still be installed with i3config, but now just a little bit easier to access, because instead of calling `bash $HOME/.i3a/feh_slides`, or equivalent, it's now just `feh-slides`.

Another benefit to this change, is that a user can have the functionality of `feh-slides`, without the need to install all of i3config, by simply running:

```bash
sudo insit feh-slides
```

By the way, if you update i3config and/or install `feh-slides`, you may wish to first run this command, to remove the old version, unless you've modified it of course:

```
rm -iv "$HOME"/.i3a/feh_slides
```

* 2018-04-13

The user's OS type and LSB will now by default be checked not long after insit is launched, but the `--ignore-os` flag has been added, in-case there are any issues and this feature needs to be bypassed.

Why was this added? Because insit is only supported on Linux, and is typically targeting Debian and Ubuntu distributions, or ones which are based thereon. It might well work in systems like Mac and BSDs, but it's not _supported_.

However, where possible, support for distributions of Linux, like Arch, is already in place.

Now checks for and addresses permission to read and write to the previous user's `last` file, if it's found. An earlier version of insit, in which the backup and restore functionality was still fresh out of the oven, the permissions weren't quite ideal; this check addresses anybody who had and used that version.

If you're using sudo on Debian, then, by default, your `HOME` environment variable will be `/root`, which is not practical with insit, given it by default will also access files in the user's `HOME` directory. This has been addressed via some checks.

* 2018-04-11

Added some very useful features which took almost two days to get right -- Here are parts of the new `--help|-h|-?` output:

```
            --restore|-R            - Restore automatically generated backups.
            --no-backup             - Do not back-up for a WHAT update.
```

Here is another important bit, from the `WARNING:` section:

```
            Backups are made, prior to updating files, and will be created after
            removing any existing back-ups of files updated with insit. This will
            occur per insit execution, only if updating, NOT per item selected.
```

As this feature can used in many ways, depending on what the user does, there may be unexpected bugs, so please be sure to report them, should you come across any; the sooner they're reported, the quicker they can be addressed and fixed.

* 2018-04-09

Added bash completion support for tozero, which is now made available when installing (or updating) tozero with insit.

* 2018-04-07

Included the newest edition to the TFL collection -- rmre -- a dangerous but incredibly useful and potentially educational utility which allows you to remove all non-essential packages from a Debian and Ubuntu system, or distributions based thereon. Obviously, not for the faint of heart.

The rmne program added earlier this morning (UK time) now has bash completion support.

* 2018-04-06

A very exciting feature I'm proud to announce, is the ability to now install insit and use it not only to download and install TFL content, but now stuff from other GitHub users! This should make insit incredibly useful if you also like to fetch content from other people who are on GitHub.

Here is an example usage of this new feature:

```bash
sudo insit -s aktsbot -C dotfiles bashrc ~/.bashrc 600 1000 1000
```

You should also be able to select the branch, using, for example `-B dev` but this particular usage is possibly yet to be ironed out.

The '--help|-h|-?' had an old example which has now been corrected to reflect the changes.

It's now possible to specify your own insit log file, using: `--logfile FILE`

* 2018-04-05

You can now check for the availability of an insit update, without actually doing anything; this could be useful for scripts, or if you simply want to check, on-the-fly.

The files `drop_terminal` and `leave_session` have been added to i3config.

* 2018-04-04

Today, I address an issue which occurred when the `--update|-U` flag was used; if no item (example: apt-undo-install) were selected, nothing would typically be displayed, whereas this is ordinarily an error.

The `term_font_size_py` file has been removed from the i3config repository, due to it being sort of unnecessary, without any worthwhile performance increase, due to the way in which the configuration file is probed for modifications. This change has been reflected here on insit, via the i3config item. If you'd like to remove what you already have, after updating insit, you can remove the file manually at: `$HOME/.i3a/term_font_size_py`

Be sure to update your `$HOME/.config/i3/config` file if you're still pointing a shortcut to the now-removed plugin.

This update initially caused a new issue to arise, by which using just `--self|-S` showed the new XERR message, which is of course not good; this has also been fixed. My apologies for any inconvenience caused by this.

Various `XERR()` messages and a `LOGIT()` message has also been added.

* 2018-03-28

At last, insit now supports wget v1.19.4, which is used in Ubuntu 18.04 and doesn't have the `--no-warc-compression` flag, for some reason. Luckily, this version of wget doesn't ask for server-side compression, at least by default, so it's all good. Gradually working to ensure my programs and configurations, especially insit (my priority at the moment) work correctly in Ubuntu 18.04.

As previously assured, I _will_ be supporting Ubuntu 18.04, and I will personally be updating my system to it when I get back from holiday a few days after the 26th of April release date -- sorry for the delay; it can't be helped, unfortunately.

If anyone is interested in helping me out, you could try out insit and my other programs and/or configurations over on Ubuntu 18.04 (any type; the more varied, the better!) then let me know of any bugs via GitHub issue reports, which I'll get to when I get back to England.

If you install bashconfig, it'll finally no longer make a futile attempt to install the `$HOME/ShellPlugin/LSPKG_Set` shell plugin, as it's now been incorporated into `lspkg` set.

* 2018-03-26

With this changelog growing in size, and surely will continue to do so, I decided it was about time users had easier access to it, via the terminal itself, instead of loading up your browser and going over to GitHub. Unfortunately, the changelog will (at least for now) display in raw form, meaning you'll see Markdown syntax.

* 2018-03-25

After some time focusing on growing the LearnLinux YouTube channel and taking part in various online Linux communities, I found myself slowing down on the code front, which I suppose is to be expected; I'm only human!

However, today I decided to work on filesitter, an old program I wrote a while back. I sometimes found myself in the situation in which I awaited the download or transfer of large files and wanted to go out or to bed, but had forgotten to accommodate this prior to running the command(s). I decided to programmatically watch the file. Of course, in retrospect, I'm sure I could've entered the command anyway and it would've executed upon completion of the previous command(s), but who cares about these details!?

In any case, filesitter can wind up being pretty useful tool, and now that it's been fixed up and updated, I felt it was worth adding to insit.

I've also worked on mif (Movie Index Filter) quite a bit, so expect updates there, but no related changes were made to insit.

* 2018-03-11

Apologies to anyone who got confused by insit insisting there's an update, no matter how many times you updated! I may or may not have accidentally forgotten to point the update check to the dev branch. Fixed now.

Using --ignore-root|-I but still having --log|-L enabled caused a lot of permission denied errors, as LOGIT() was still being called and attempted processing of the logfile. This has been fixed.

* 2018-03-08

One thing which I personally found irritating since the new update notification feature in insit, was being told there was a new version, _while_ updating to said version! This is now thankfully resolved.

* 2018-03-06

Today is a good day for insit, as it gets plenty of optimizations and overall improvements, from logging to the messages the user will see. I've also published new content, which has been reflected in the latest insit update. If you've yet to update insit, I strongly recommend that you do, as there have been some fairly important changes.

Another good bit of news, is that finally insit will make it known when an update is available; it's up to the user whether he or she wishes to actually perform that update. This check is done very simply by checking the file 'version' stored in the installit repository. This has been something I've wanted to do for ages. May include the latest CHANGELOG.md update to the update availability notification the user sees; worth it?

The caveat to this availability check, is that it won't know whether changes were made until I update that version file, and, until the next day.

* 2018-03-06

Apologies go to whomever may have used vimconfig before it was ready. I made the jump a little too soon, but after several hours today, it's now all sorted, and vimconfig is ready to rock 'n' roll!

* 2018-03-04

Moved over to the new version (date) format, and the norm will now be to have a `--version|-v` flag which displays this. The reason for this change, is that I got sick of updating the header's timestamp (courtesy of a shortcut I added to VIM), and then having to change the `--help` output's version as well!

Now when I use the aforementioned shortcut, it updates the `_VERSION_` variable as well as the header, plus it clears out any stranded tabs and spaces. See `miscellaneous/.vimrc` for how I did this. Lastly, as an added bonus, this `--version|-v` flag allows for easy parsing of tfl programs, open the doors for later tfl program update checks via insit; this is something I've been thinking of incorporating for a while now.

Feedback welcome.

* 2018-02-25

Logging is now more aggressive, to further assist any debugging endeavors. I've also added the ability to view the logging output while using insit, using the `--verbose` or `-v` flags; this should work whether logging is enabled or not, but of course the intended result is that logging won't be saved, just shown.

Uninstalling items available using insit, now supports gvfs-trash, meaning insit will send files to trash, rather than permanently deleting them. This is only done if gvfs-trash is detected by insit. The user will be informed, as usual.

* 2018-02-23

At long last, insit now support wget version 1.19.2.

* 2018-02-15

The file APT_Update_Cron now gets correctly added to /etc/cron.hourly when notify-upgrade is installed, instead of /etc/cron.daily.

* 2018-02-12

Using -L and --ignore-root results in admittedly excessive amounts of ERRORs (L0141).

* 2018-02-02

The small lsbins shell program has been moved to miscellaneous; it doesn't really merit having a repository of its own, since it's so small and basic, with little need for any big updates.

If you'd like to install lsbins, or update an existing installation thereof, then please *update* insit beforehand.

Sometimes, while it works as expected, updating insit still yields this result:

```
$ sudo insit -S
File '/usr/bin/insit' downloaded and updated.
File '/usr/bin/insit' ownership re-set.
File '/usr/bin/insit' mode re-set.
File '/usr/share/bash-completion/completions/insit' downloaded and updated.
File '/usr/share/bash-completion/completions/insit' ownership re-set.
File '/usr/share/bash-completion/completions/insit' mode re-set.
/usr/bin/insit: line 227: it: command not found
/usr/bin/insit: line 228: syntax error near unexpected token `fi'
/usr/bin/insit: line 228: `fi'
```

I'm hoping the latest commit(s) will fix this. As a result of this hopefully-a-fix, it'll no longer be possible to update insit _and_ install and/or update something. This will likely be revised at a later date.

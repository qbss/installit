* 2018-03-28

At last, insit now supports wget v1.19.4, which is used in Ubuntu 18.04 and doesn't have the `--no-warc-compression` flag, for some reason. Luckily, this version of wget doesn't ask for server-side compression, at least by default, so it's all good. Gradually working to ensure my programs and configurations, especially insit (my priority at the moment) work correctly in Ubuntu 18.04.

As previously assured, I _will_ be supporting Ubuntu 18.04, and I will personally be updating my system to it when I get back from holiday a few days after the 26th of April release date -- sorry for the delay; it can't be helped, unfortunately.

If anyone is interested in helping me out, you could try out insit and my other programs and/or configurations over on Ubuntu 18.04 (any type; the more varied, the better!) then let me know of any bugs via GitHub issue reports, which I'll get to when I get back to England.

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

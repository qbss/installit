* 2018-03-06

Today is a good day for insit, as it gets plenty of optimizations and overall improvements, from logging to the messages the user will see. I've also published new content, which has been reflected in the latest insit update. If you've yet to update insit, I strongly recommend that you do, as there have been some fairly important changes.

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
